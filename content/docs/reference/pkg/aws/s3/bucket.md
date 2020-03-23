
---
title: "Bucket"
block_external_search_index: true
---

Provides a S3 bucket resource.

## Example Usage

### Private Bucket w/ Tags

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("b", {
    acl: "private",
    tags: {
        Environment: "Dev",
        Name: "My bucket",
    },
});
```

### Static Website Hosting

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as fs from "fs";

const bucket = new aws.s3.Bucket("b", {
    acl: "public-read",
    policy: fs.readFileSync("policy.json", "utf-8"),
    website: {
        errorDocument: "error.html",
        indexDocument: "index.html",
        routingRules: `[{
    "Condition": {
        "KeyPrefixEquals": "docs/"
    },
    "Redirect": {
        "ReplaceKeyPrefixWith": "documents/"
    }
}]
`,
    },
});
```

### Using CORS

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("b", {
    acl: "public-read",
    corsRules: [{
        allowedHeaders: ["*"],
        allowedMethods: [
            "PUT",
            "POST",
        ],
        allowedOrigins: ["https://s3-website-test.mydomain.com"],
        exposeHeaders: ["ETag"],
        maxAgeSeconds: 3000,
    }],
});
```

### Using versioning

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("b", {
    acl: "private",
    versioning: {
        enabled: true,
    },
});
```

### Enable Logging

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const logBucket = new aws.s3.Bucket("log_bucket", {
    acl: "log-delivery-write",
});
const bucket = new aws.s3.Bucket("b", {
    acl: "private",
    loggings: [{
        targetBucket: logBucket.id,
        targetPrefix: "log/",
    }],
});
```

### Using object lifecycle

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("bucket", {
    acl: "private",
    lifecycleRules: [
        {
            enabled: true,
            expiration: {
                days: 90,
            },
            id: "log",
            prefix: "log/",
            tags: {
                autoclean: "true",
                rule: "log",
            },
            transitions: [
                {
                    days: 30,
                    storageClass: "STANDARD_IA", // or "ONEZONE_IA"
                },
                {
                    days: 60,
                    storageClass: "GLACIER",
                },
            ],
        },
        {
            enabled: true,
            expiration: {
                date: "2016-01-12",
            },
            id: "tmp",
            prefix: "tmp/",
        },
    ],
});
const versioningBucket = new aws.s3.Bucket("versioning_bucket", {
    acl: "private",
    lifecycleRules: [{
        enabled: true,
        noncurrentVersionExpiration: {
            days: 90,
        },
        noncurrentVersionTransitions: [
            {
                days: 30,
                storageClass: "STANDARD_IA",
            },
            {
                days: 60,
                storageClass: "GLACIER",
            },
        ],
        prefix: "config/",
    }],
    versioning: {
        enabled: true,
    },
});
```

### Using replication configuration

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const central = new aws.Provider("central", {
    region: "eu-central-1",
});
const replicationRole = new aws.iam.Role("replication", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "s3.amazonaws.com"
      },
      "Effect": "Allow",
      "Sid": ""
    }
  ]
}
`,
});
const destination = new aws.s3.Bucket("destination", {
    region: "eu-west-1",
    versioning: {
        enabled: true,
    },
});
const bucket = new aws.s3.Bucket("bucket", {
    acl: "private",
    region: "eu-central-1",
    replicationConfiguration: {
        role: replicationRole.arn,
        rules: [{
            destination: {
                bucket: destination.arn,
                storageClass: "STANDARD",
            },
            id: "foobar",
            prefix: "foo",
            status: "Enabled",
        }],
    },
    versioning: {
        enabled: true,
    },
}, {provider: central});
const replicationPolicy = new aws.iam.Policy("replication", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "s3:GetReplicationConfiguration",
        "s3:ListBucket"
      ],
      "Effect": "Allow",
      "Resource": [
        "${bucket.arn}"
      ]
    },
    {
      "Action": [
        "s3:GetObjectVersion",
        "s3:GetObjectVersionAcl"
      ],
      "Effect": "Allow",
      "Resource": [
        "${bucket.arn}/*"
      ]
    },
    {
      "Action": [
        "s3:ReplicateObject",
        "s3:ReplicateDelete"
      ],
      "Effect": "Allow",
      "Resource": "${destination.arn}/*"
    }
  ]
}
`,
});
const replicationRolePolicyAttachment = new aws.iam.RolePolicyAttachment("replication", {
    policyArn: replicationPolicy.arn,
    role: replicationRole.name,
});
```

### Enable Default Server Side Encryption

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const mykey = new aws.kms.Key("mykey", {
    deletionWindowInDays: 10,
    description: "This key is used to encrypt bucket objects",
});
const mybucket = new aws.s3.Bucket("mybucket", {
    serverSideEncryptionConfiguration: {
        rule: {
            applyServerSideEncryptionByDefault: {
                kmsMasterKeyId: mykey.arn,
                sseAlgorithm: "aws:kms",
            },
        },
    },
});
```

### Using ACL policy grants

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const currentUser = aws.getCanonicalUserId();
const bucket = new aws.s3.Bucket("bucket", {
    grant: [
        {
            id: currentUser.id,
            permission: ["FULL_ACCESS"],
            type: "CanonicalUser",
        },
        {
            permission: [
                "READ",
                "WRITE",
            ],
            type: "Group",
            uri: "http://acs.amazonaws.com/groups/s3/LogDelivery",
        },
    ],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/s3_bucket.html.markdown.



## Create a Bucket Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#Bucket">Bucket</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketArgs">BucketArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Bucket</span><span class="p">(resource_name, opts=None, </span>acceleration_status=None<span class="p">, </span>acl=None<span class="p">, </span>arn=None<span class="p">, </span>bucket=None<span class="p">, </span>bucket_prefix=None<span class="p">, </span>cors_rules=None<span class="p">, </span>force_destroy=None<span class="p">, </span>grants=None<span class="p">, </span>hosted_zone_id=None<span class="p">, </span>lifecycle_rules=None<span class="p">, </span>loggings=None<span class="p">, </span>object_lock_configuration=None<span class="p">, </span>policy=None<span class="p">, </span>region=None<span class="p">, </span>replication_configuration=None<span class="p">, </span>request_payer=None<span class="p">, </span>server_side_encryption_configuration=None<span class="p">, </span>tags=None<span class="p">, </span>versioning=None<span class="p">, </span>website=None<span class="p">, </span>website_domain=None<span class="p">, </span>website_endpoint=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucket<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketArgs">BucketArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#Bucket">Bucket</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.Bucket.html">Bucket</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketArgs.html">BucketArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Contructor Arguments

{{% choosable language nodejs %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

Resource Arguments




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">List&lt;Bucket<wbr>Cors<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">List&lt;Bucket<wbr>Grant<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">List&lt;Bucket<wbr>Lifecycle<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">List&lt;Bucket<wbr>Logging<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Bucket<wbr>Replication<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Bucket<wbr>Website<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">[]Bucket<wbr>Cors<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">[]Bucket<wbr>Grant</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">[]Bucket<wbr>Lifecycle<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">[]Bucket<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">*Bucket<wbr>Object<wbr>Lock<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">*Bucket<wbr>Replication<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">*Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">*Bucket<wbr>Versioning</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">*Bucket<wbr>Website</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">string | CannedAcl</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">Bucket<wbr>Cors<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">Bucket<wbr>Grant[]?</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">Bucket<wbr>Lifecycle<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">Bucket<wbr>Logging[]?</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Bucket<wbr>Object<wbr>Lock<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">string | PolicyDocument</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Bucket<wbr>Replication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning?</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Bucket<wbr>Website?</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acceleration_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cors_<wbr>rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">List[Bucket<wbr>Cors<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">List[Bucket<wbr>Grant]</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle_<wbr>rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">List[Bucket<wbr>Lifecycle<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">List[Bucket<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Dict[Bucket<wbr>Object<wbr>Lock<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Dict[Bucket<wbr>Replication<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>payer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Dict[Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Dict[Bucket<wbr>Versioning]</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Dict[Bucket<wbr>Website]</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website_<wbr>domain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Bucket Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Regional<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">List&lt;Bucket<wbr>Cors<wbr>Rule&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">List&lt;Bucket<wbr>Grant&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">List&lt;Bucket<wbr>Lifecycle<wbr>Rule&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">List&lt;Bucket<wbr>Logging&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Bucket<wbr>Object<wbr>Lock<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Bucket<wbr>Replication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Bucket<wbr>Website?</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Regional<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">[]Bucket<wbr>Cors<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">[]Bucket<wbr>Grant</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">[]Bucket<wbr>Lifecycle<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">[]Bucket<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">*Bucket<wbr>Object<wbr>Lock<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">*Bucket<wbr>Replication<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">*Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">*Bucket<wbr>Website</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<wbr>Regional<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">Bucket<wbr>Cors<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">Bucket<wbr>Grant[]?</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">Bucket<wbr>Lifecycle<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">Bucket<wbr>Logging[]?</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Bucket<wbr>Object<wbr>Lock<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Bucket<wbr>Replication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-"
            title="">versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Bucket<wbr>Website?</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-"
            title="">website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">acceleration_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket_<wbr>domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket_<wbr>regional_<wbr>domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cors_<wbr>rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">List[Bucket<wbr>Cors<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">List[Bucket<wbr>Grant]</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lifecycle_<wbr>rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">List[Bucket<wbr>Lifecycle<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">List[Bucket<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">object_<wbr>lock_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Dict[Bucket<wbr>Object<wbr>Lock<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Dict[Bucket<wbr>Replication<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">request_<wbr>payer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">server_<wbr>side_<wbr>encryption_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Dict[Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-"
            title="">versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Dict[Bucket<wbr>Versioning]</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Dict[Bucket<wbr>Website]</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">website_<wbr>domain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-"
            title="">website_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Bucket Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketState">BucketState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#Bucket">Bucket</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>acceleration_status=None<span class="p">, </span>acl=None<span class="p">, </span>arn=None<span class="p">, </span>bucket=None<span class="p">, </span>bucket_domain_name=None<span class="p">, </span>bucket_prefix=None<span class="p">, </span>bucket_regional_domain_name=None<span class="p">, </span>cors_rules=None<span class="p">, </span>force_destroy=None<span class="p">, </span>grants=None<span class="p">, </span>hosted_zone_id=None<span class="p">, </span>lifecycle_rules=None<span class="p">, </span>loggings=None<span class="p">, </span>object_lock_configuration=None<span class="p">, </span>policy=None<span class="p">, </span>region=None<span class="p">, </span>replication_configuration=None<span class="p">, </span>request_payer=None<span class="p">, </span>server_side_encryption_configuration=None<span class="p">, </span>tags=None<span class="p">, </span>versioning=None<span class="p">, </span>website=None<span class="p">, </span>website_domain=None<span class="p">, </span>website_endpoint=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucket<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketState">BucketState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#Bucket">Bucket</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.Bucket.html">Bucket</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketState.html">BucketState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Bucket resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

{{% lang nodejs %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>id</strong> &ndash; (Required) The _unique_ provider ID of the resource to lookup.</li>
    <li><strong>state</strong> &ndash; (Optional) Any extra arguments used during the lookup.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang go %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>id</strong> &ndash; (Required) The _unique_ provider ID of the resource to lookup.</li>
    <li><strong>state</strong> &ndash; (Optional) Any extra arguments used during the lookup.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang csharp %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>id</strong> &ndash; (Required) The _unique_ provider ID of the resource to lookup.</li>
    <li><strong>state</strong> &ndash; (Optional) Any extra arguments used during the lookup.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

The following state arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Regional<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">List&lt;Bucket<wbr>Cors<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">List&lt;Bucket<wbr>Grant<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">List&lt;Bucket<wbr>Lifecycle<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">List&lt;Bucket<wbr>Logging<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Bucket<wbr>Replication<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Bucket<wbr>Website<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Regional<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">[]Bucket<wbr>Cors<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">[]Bucket<wbr>Grant</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">[]Bucket<wbr>Lifecycle<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">[]Bucket<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">*Bucket<wbr>Object<wbr>Lock<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">*Bucket<wbr>Replication<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">*Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">*Bucket<wbr>Versioning</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">*Bucket<wbr>Website</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acceleration<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">string | CannedAcl</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<wbr>Regional<wbr>Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cors<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">Bucket<wbr>Cors<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">Bucket<wbr>Grant[]?</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">Bucket<wbr>Lifecycle<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">Bucket<wbr>Logging[]?</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Bucket<wbr>Object<wbr>Lock<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">string | PolicyDocument</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Bucket<wbr>Replication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request<wbr>Payer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Bucket<wbr>Versioning?</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Bucket<wbr>Website?</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acceleration_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sets the accelerate configuration of an existing bucket. Can be `Enabled` or `Suspended`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.  Conflicts with `grant`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the bucket. Will be of format `arn:aws:s3:::bucketname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket_<wbr>domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bucket domain name. Will be of format `bucketname.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique bucket name beginning with the specified prefix. Conflicts with `bucket`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket_<wbr>regional_<wbr>domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bucket region-specific domain name. The bucket domain name including the region name, please refer [here](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) for format. Note: The AWS CloudFront allows specifying S3 region-specific endpoint when creating S3 origin, it will prevent [redirect issues](https://forums.aws.amazon.com/thread.jspa?threadID=216814) from CloudFront to S3 Origin URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cors_<wbr>rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketcorsrule">List[Bucket<wbr>Cors<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A rule of [Cross-Origin Resource Sharing](https://docs.aws.amazon.com/AmazonS3/latest/dev/cors.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all objects (including any [locked objects](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html)) should be deleted from the bucket so that the bucket can be destroyed without error. These objects are *not* recoverable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grants<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketgrant">List[Bucket<wbr>Grant]</a></span>
    </dt>
    <dd>{{% md %}}An [ACL policy grant](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#sample-acl) (documented below). Conflicts with `acl`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [Route 53 Hosted Zone ID](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_website_region_endpoints) for this bucket&#39;s region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle_<wbr>rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerule">List[Bucket<wbr>Lifecycle<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [object lifecycle management](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">loggings<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlogging">List[Bucket<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}A settings of [bucket logging](https://docs.aws.amazon.com/AmazonS3/latest/UG/ManagingBucketLogging.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfiguration">Dict[Bucket<wbr>Object<wbr>Lock<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [S3 object locking](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A valid [bucket policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-bucket-policies.html) JSON document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If specified, the AWS region this bucket should reside in. Otherwise, the region used by the callee.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfiguration">Dict[Bucket<wbr>Replication<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [replication configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html) (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">request_<wbr>payer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies who should bear the cost of Amazon S3 data transfer.
Can be either `BucketOwner` or `Requester`. By default, the owner of the S3 bucket would incur
the costs of any data transfer. See [Requester Pays Buckets](http://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html)
developer guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfiguration">Dict[Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A configuration of [server-side encryption configuration](http://docs.aws.amazon.com/AmazonS3/latest/dev/bucket-encryption.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">versioning<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketversioning">Dict[Bucket<wbr>Versioning]</a></span>
    </dt>
    <dd>{{% md %}}A state of [versioning](https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html) (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketwebsite">Dict[Bucket<wbr>Website]</a></span>
    </dt>
    <dd>{{% md %}}A website object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website_<wbr>domain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The domain of the website endpoint, if the bucket is configured with a website. If not, this will be an empty string. This is used to create Route 53 alias records.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The website endpoint, if the bucket is configured with a website. If not, this will be an empty string.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### BucketCorsRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketCorsRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketCorsRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketCorsRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketCorsRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketCorsRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketCorsRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies which headers are allowed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Specifies which methods are allowed. Can be `GET`, `PUT`, `POST`, `DELETE` or `HEAD`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Allowed<wbr>Origins<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Specifies which origins are allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expose<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies expose header in the response.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Age<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Specifies time in seconds that browser can cache the response for a preflight request.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies which headers are allowed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies which methods are allowed. Can be `GET`, `PUT`, `POST`, `DELETE` or `HEAD`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Allowed<wbr>Origins<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies which origins are allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expose<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies expose header in the response.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Age<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Specifies time in seconds that browser can cache the response for a preflight request.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies which headers are allowed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Specifies which methods are allowed. Can be `GET`, `PUT`, `POST`, `DELETE` or `HEAD`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">allowed<wbr>Origins<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Specifies which origins are allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expose<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies expose header in the response.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Age<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Specifies time in seconds that browser can cache the response for a preflight request.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies which headers are allowed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies which methods are allowed. Can be `GET`, `PUT`, `POST`, `DELETE` or `HEAD`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">allowed<wbr>Origins<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies which origins are allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expose<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies expose header in the response.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Age<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specifies time in seconds that browser can cache the response for a preflight request.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketGrant
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketGrant">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketGrant">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketGrantArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketGrantOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketGrantArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketGrant.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Permissions<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of permissions to apply for grantee. Valid values are `READ`, `WRITE`, `READ_ACP`, `WRITE_ACP`, `FULL_ACCESS`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}- Type of grantee to apply for. Valid values are `CanonicalUser` and `Group`. `AmazonCustomerByEmail` is not supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Uri address to grant for. Used only when `type` is `Group`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Permissions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of permissions to apply for grantee. Valid values are `READ`, `WRITE`, `READ_ACP`, `WRITE_ACP`, `FULL_ACCESS`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}- Type of grantee to apply for. Valid values are `CanonicalUser` and `Group`. `AmazonCustomerByEmail` is not supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Uri address to grant for. Used only when `type` is `Group`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">permissions<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of permissions to apply for grantee. Valid values are `READ`, `WRITE`, `READ_ACP`, `WRITE_ACP`, `FULL_ACCESS`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}- Type of grantee to apply for. Valid values are `CanonicalUser` and `Group`. `AmazonCustomerByEmail` is not supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Uri address to grant for. Used only when `type` is `Group`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">permissions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of permissions to apply for grantee. Valid values are `READ`, `WRITE`, `READ_ACP`, `WRITE_ACP`, `FULL_ACCESS`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}- Type of grantee to apply for. Valid values are `CanonicalUser` and `Group`. `AmazonCustomerByEmail` is not supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Uri address to grant for. Used only when `type` is `Group`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketLifecycleRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketLifecycleRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketLifecycleRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Abort<wbr>Incomplete<wbr>Multipart<wbr>Upload<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after initiating a multipart upload when the multipart upload must be completed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruleexpiration">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Expiration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Noncurrent<wbr>Version<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversionexpiration">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Expiration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Noncurrent<wbr>Version<wbr>Transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversiontransition">List&lt;Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Transition<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions transitions (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruletransition">List&lt;Bucket<wbr>Lifecycle<wbr>Rule<wbr>Transition<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s transitions (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Abort<wbr>Incomplete<wbr>Multipart<wbr>Upload<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after initiating a multipart upload when the multipart upload must be completed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruleexpiration">*Bucket<wbr>Lifecycle<wbr>Rule<wbr>Expiration</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Noncurrent<wbr>Version<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversionexpiration">*Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Expiration</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Noncurrent<wbr>Version<wbr>Transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversiontransition">[]Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Transition</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions transitions (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruletransition">[]Bucket<wbr>Lifecycle<wbr>Rule<wbr>Transition</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s transitions (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">abort<wbr>Incomplete<wbr>Multipart<wbr>Upload<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after initiating a multipart upload when the multipart upload must be completed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruleexpiration">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Expiration?</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">noncurrent<wbr>Version<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversionexpiration">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Expiration?</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">noncurrent<wbr>Version<wbr>Transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversiontransition">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Transition[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions transitions (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruletransition">Bucket<wbr>Lifecycle<wbr>Rule<wbr>Transition[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s transitions (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">abort<wbr>Incomplete<wbr>Multipart<wbr>Upload<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after initiating a multipart upload when the multipart upload must be completed.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruleexpiration">Dict[Bucket<wbr>Lifecycle<wbr>Rule<wbr>Expiration]</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">noncurrent<wbr>Version<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversionexpiration">Dict[Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Expiration]</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions expire (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">noncurrent<wbr>Version<wbr>Transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecyclerulenoncurrentversiontransition">List[Bucket<wbr>Lifecycle<wbr>Rule<wbr>Noncurrent<wbr>Version<wbr>Transition]</a></span>
    </dt>
    <dd>{{% md %}}Specifies when noncurrent object versions transitions (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transitions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketlifecycleruletransition">List[Bucket<wbr>Lifecycle<wbr>Rule<wbr>Transition]</a></span>
    </dt>
    <dd>{{% md %}}Specifies a period in the object&#39;s transitions (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketLifecycleRuleExpiration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketLifecycleRuleExpiration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketLifecycleRuleExpiration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleExpirationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleExpirationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleExpirationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleExpiration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expired<wbr>Object<wbr>Delete<wbr>Marker<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}On a versioned bucket (versioning-enabled or versioning-suspended bucket), you can add this element in the lifecycle configuration to direct Amazon S3 to delete expired object delete markers.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expired<wbr>Object<wbr>Delete<wbr>Marker<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}On a versioned bucket (versioning-enabled or versioning-suspended bucket), you can add this element in the lifecycle configuration to direct Amazon S3 to delete expired object delete markers.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expired<wbr>Object<wbr>Delete<wbr>Marker<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}On a versioned bucket (versioning-enabled or versioning-suspended bucket), you can add this element in the lifecycle configuration to direct Amazon S3 to delete expired object delete markers.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expired<wbr>Object<wbr>Delete<wbr>Marker<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}On a versioned bucket (versioning-enabled or versioning-suspended bucket), you can add this element in the lifecycle configuration to direct Amazon S3 to delete expired object delete markers.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketLifecycleRuleNoncurrentVersionExpiration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketLifecycleRuleNoncurrentVersionExpiration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketLifecycleRuleNoncurrentVersionExpiration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleNoncurrentVersionExpirationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleNoncurrentVersionExpirationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleNoncurrentVersionExpirationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleNoncurrentVersionExpiration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketLifecycleRuleNoncurrentVersionTransition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketLifecycleRuleNoncurrentVersionTransition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketLifecycleRuleNoncurrentVersionTransition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleNoncurrentVersionTransitionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleNoncurrentVersionTransitionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleNoncurrentVersionTransitionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleNoncurrentVersionTransition.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketLifecycleRuleTransition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketLifecycleRuleTransition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketLifecycleRuleTransition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleTransitionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLifecycleRuleTransitionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleTransitionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLifecycleRuleTransition.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the date after which you want the corresponding action to take effect.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketLogging
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketLogging">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketLogging">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLoggingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketLoggingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLoggingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketLogging.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Target<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that will receive the log objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}To specify a key prefix for log objects.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Target<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that will receive the log objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}To specify a key prefix for log objects.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">target<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that will receive the log objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}To specify a key prefix for log objects.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">target<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that will receive the log objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}To specify a key prefix for log objects.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketObjectLockConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketObjectLockConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketObjectLockConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectLockConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectLockConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectLockConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectLockConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Object<wbr>Lock<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this bucket has an Object Lock configuration enabled. Valid value is `Enabled`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationrule">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Object<wbr>Lock<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this bucket has an Object Lock configuration enabled. Valid value is `Enabled`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationrule">*Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">object<wbr>Lock<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this bucket has an Object Lock configuration enabled. Valid value is `Enabled`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationrule">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule?</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">object<wbr>Lock<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether this bucket has an Object Lock configuration enabled. Valid value is `Enabled`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationrule">Dict[Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketObjectLockConfigurationRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketObjectLockConfigurationRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketObjectLockConfigurationRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectLockConfigurationRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectLockConfigurationRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectLockConfigurationRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectLockConfigurationRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Default<wbr>Retention<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationruledefaultretention">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule<wbr>Default<wbr>Retention<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The default retention period that you want to apply to new objects placed in this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Default<wbr>Retention<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationruledefaultretention">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule<wbr>Default<wbr>Retention</a></span>
    </dt>
    <dd>{{% md %}}The default retention period that you want to apply to new objects placed in this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">default<wbr>Retention<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationruledefaultretention">Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule<wbr>Default<wbr>Retention</a></span>
    </dt>
    <dd>{{% md %}}The default retention period that you want to apply to new objects placed in this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">default<wbr>Retention<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketobjectlockconfigurationruledefaultretention">Dict[Bucket<wbr>Object<wbr>Lock<wbr>Configuration<wbr>Rule<wbr>Default<wbr>Retention]</a></span>
    </dt>
    <dd>{{% md %}}The default retention period that you want to apply to new objects placed in this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketObjectLockConfigurationRuleDefaultRetention
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketObjectLockConfigurationRuleDefaultRetention">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketObjectLockConfigurationRuleDefaultRetention">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectLockConfigurationRuleDefaultRetentionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectLockConfigurationRuleDefaultRetentionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectLockConfigurationRuleDefaultRetentionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectLockConfigurationRuleDefaultRetention.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default Object Lock retention mode you want to apply to new objects placed in this bucket. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Years<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of years that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default Object Lock retention mode you want to apply to new objects placed in this bucket. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Years<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of years that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The default Object Lock retention mode you want to apply to new objects placed in this bucket. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">years<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of years that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that you want to specify for the default retention period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default Object Lock retention mode you want to apply to new objects placed in this bucket. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">years<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of years that you want to specify for the default retention period.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role for Amazon S3 to assume when replicating the objects.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrule">List&lt;Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Specifies the rules managing the replication (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role for Amazon S3 to assume when replicating the objects.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrule">[]Bucket<wbr>Replication<wbr>Configuration<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the rules managing the replication (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role for Amazon S3 to assume when replicating the objects.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrule">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the rules managing the replication (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role for Amazon S3 to assume when replicating the objects.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrule">List[Bucket<wbr>Replication<wbr>Configuration<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the rules managing the replication (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfigurationRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfigurationRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfigurationRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestination">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Specifies the destination for the rule (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulefilter">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Filter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Filter that identifies subset of objects to which the replication rule applies (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The priority associated with the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Selection<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteria">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies special object selection criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the rule. Either `Enabled` or `Disabled`. The rule is ignored if status is not Enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestination">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Specifies the destination for the rule (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulefilter">*Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Filter that identifies subset of objects to which the replication rule applies (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The priority associated with the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Selection<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteria">*Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria</a></span>
    </dt>
    <dd>{{% md %}}Specifies special object selection criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the rule. Either `Enabled` or `Disabled`. The rule is ignored if status is not Enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestination">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Specifies the destination for the rule (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulefilter">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Filter?</a></span>
    </dt>
    <dd>{{% md %}}Filter that identifies subset of objects to which the replication rule applies (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The priority associated with the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Selection<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteria">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria?</a></span>
    </dt>
    <dd>{{% md %}}Specifies special object selection criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the rule. Either `Enabled` or `Disabled`. The rule is ignored if status is not Enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestination">Dict[Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the destination for the rule (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulefilter">Dict[Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Filter that identifies subset of objects to which the replication rule applies (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Canonical user id to grant for. Used only when `type` is `CanonicalUser`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority associated with the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Selection<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteria">Dict[Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria]</a></span>
    </dt>
    <dd>{{% md %}}Specifies special object selection criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the rule. Either `Enabled` or `Disabled`. The rule is ignored if status is not Enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfigurationRuleDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfigurationRuleDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfigurationRuleDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleDestination.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Control<wbr>Translation<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestinationaccesscontroltranslation">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination<wbr>Access<wbr>Control<wbr>Translation<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the overrides to use for object owners on replication. Must be used in conjunction with `account_id` owner override configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Account ID to use for overriding the object owner on replication. Must be used in conjunction with `access_control_translation` override configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replica<wbr>Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Destination KMS encryption key ARN for SSE-KMS replication. Must be used in conjunction with
`sse_kms_encrypted_objects` source selection criteria.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Control<wbr>Translation<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestinationaccesscontroltranslation">*Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination<wbr>Access<wbr>Control<wbr>Translation</a></span>
    </dt>
    <dd>{{% md %}}Specifies the overrides to use for object owners on replication. Must be used in conjunction with `account_id` owner override configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Account ID to use for overriding the object owner on replication. Must be used in conjunction with `access_control_translation` override configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replica<wbr>Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Destination KMS encryption key ARN for SSE-KMS replication. Must be used in conjunction with
`sse_kms_encrypted_objects` source selection criteria.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Control<wbr>Translation<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestinationaccesscontroltranslation">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination<wbr>Access<wbr>Control<wbr>Translation?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the overrides to use for object owners on replication. Must be used in conjunction with `account_id` owner override configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Account ID to use for overriding the object owner on replication. Must be used in conjunction with `access_control_translation` override configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replica<wbr>Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Destination KMS encryption key ARN for SSE-KMS replication. Must be used in conjunction with
`sse_kms_encrypted_objects` source selection criteria.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Control<wbr>Translation<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationruledestinationaccesscontroltranslation">Dict[Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Destination<wbr>Access<wbr>Control<wbr>Translation]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the overrides to use for object owners on replication. Must be used in conjunction with `account_id` owner override configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Account ID to use for overriding the object owner on replication. Must be used in conjunction with `access_control_translation` override configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the S3 bucket where you want Amazon S3 to store replicas of the object identified by the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replica<wbr>Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Destination KMS encryption key ARN for SSE-KMS replication. Must be used in conjunction with
`sse_kms_encrypted_objects` source selection criteria.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The class of storage used to store the object. Can be `STANDARD`, `REDUCED_REDUNDANCY`, `STANDARD_IA`, `ONEZONE_IA`, `INTELLIGENT_TIERING`, `GLACIER`, or `DEEP_ARCHIVE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfigurationRuleDestinationAccessControlTranslation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfigurationRuleDestinationAccessControlTranslation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfigurationRuleDestinationAccessControlTranslation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleDestinationAccessControlTranslationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleDestinationAccessControlTranslationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleDestinationAccessControlTranslationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleDestinationAccessControlTranslation.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The override value for the owner on replicated objects. Currently only `Destination` is supported.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The override value for the owner on replicated objects. Currently only `Destination` is supported.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The override value for the owner on replicated objects. Currently only `Destination` is supported.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The override value for the owner on replicated objects. Currently only `Destination` is supported.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfigurationRuleFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfigurationRuleFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfigurationRuleFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object keyname prefix that identifies subset of objects to which the rule applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags that identifies subset of objects to which the rule applies.
The rule applies only to objects having all the tags in its tagset.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfigurationRuleSourceSelectionCriteria
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfigurationRuleSourceSelectionCriteria">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfigurationRuleSourceSelectionCriteria">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleSourceSelectionCriteriaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleSourceSelectionCriteriaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleSourceSelectionCriteriaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleSourceSelectionCriteria.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Sse<wbr>Kms<wbr>Encrypted<wbr>Objects<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteriassekmsencryptedobjects">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria<wbr>Sse<wbr>Kms<wbr>Encrypted<wbr>Objects<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Match SSE-KMS encrypted objects (documented below). If specified, `replica_kms_key_id`
in `destination` must be specified as well.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Sse<wbr>Kms<wbr>Encrypted<wbr>Objects<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteriassekmsencryptedobjects">*Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria<wbr>Sse<wbr>Kms<wbr>Encrypted<wbr>Objects</a></span>
    </dt>
    <dd>{{% md %}}Match SSE-KMS encrypted objects (documented below). If specified, `replica_kms_key_id`
in `destination` must be specified as well.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">sse<wbr>Kms<wbr>Encrypted<wbr>Objects<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteriassekmsencryptedobjects">Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria<wbr>Sse<wbr>Kms<wbr>Encrypted<wbr>Objects?</a></span>
    </dt>
    <dd>{{% md %}}Match SSE-KMS encrypted objects (documented below). If specified, `replica_kms_key_id`
in `destination` must be specified as well.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">sse<wbr>Kms<wbr>Encrypted<wbr>Objects<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketreplicationconfigurationrulesourceselectioncriteriassekmsencryptedobjects">Dict[Bucket<wbr>Replication<wbr>Configuration<wbr>Rule<wbr>Source<wbr>Selection<wbr>Criteria<wbr>Sse<wbr>Kms<wbr>Encrypted<wbr>Objects]</a></span>
    </dt>
    <dd>{{% md %}}Match SSE-KMS encrypted objects (documented below). If specified, `replica_kms_key_id`
in `destination` must be specified as well.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjects
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjects">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjects">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjectsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjectsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjectsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketReplicationConfigurationRuleSourceSelectionCriteriaSseKmsEncryptedObjects.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketServerSideEncryptionConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketServerSideEncryptionConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketServerSideEncryptionConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketServerSideEncryptionConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketServerSideEncryptionConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketServerSideEncryptionConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketServerSideEncryptionConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationrule">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationrule">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationrule">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationrule">Dict[Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}The Object Lock rule in place for this bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketServerSideEncryptionConfigurationRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketServerSideEncryptionConfigurationRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketServerSideEncryptionConfigurationRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketServerSideEncryptionConfigurationRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketServerSideEncryptionConfigurationRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketServerSideEncryptionConfigurationRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketServerSideEncryptionConfigurationRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationruleapplyserversideencryptionbydefault">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule<wbr>Apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}A single object for setting server-side encryption by default. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationruleapplyserversideencryptionbydefault">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule<wbr>Apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default</a></span>
    </dt>
    <dd>{{% md %}}A single object for setting server-side encryption by default. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationruleapplyserversideencryptionbydefault">Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule<wbr>Apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default</a></span>
    </dt>
    <dd>{{% md %}}A single object for setting server-side encryption by default. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketserversideencryptionconfigurationruleapplyserversideencryptionbydefault">Dict[Bucket<wbr>Server<wbr>Side<wbr>Encryption<wbr>Configuration<wbr>Rule<wbr>Apply<wbr>Server<wbr>Side<wbr>Encryption<wbr>By<wbr>Default]</a></span>
    </dt>
    <dd>{{% md %}}A single object for setting server-side encryption by default. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefault
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefault">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefault">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefaultArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefaultOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefaultArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketServerSideEncryptionConfigurationRuleApplyServerSideEncryptionByDefault.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS KMS master key ID used for the SSE-KMS encryption. This can only be used when you set the value of `sse_algorithm` as `aws:kms`. The default `aws/s3` AWS KMS master key is used if this element is absent while the `sse_algorithm` is `aws:kms`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sse<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The server-side encryption algorithm to use. Valid values are `AES256` and `aws:kms`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS KMS master key ID used for the SSE-KMS encryption. This can only be used when you set the value of `sse_algorithm` as `aws:kms`. The default `aws/s3` AWS KMS master key is used if this element is absent while the `sse_algorithm` is `aws:kms`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sse<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The server-side encryption algorithm to use. Valid values are `AES256` and `aws:kms`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS KMS master key ID used for the SSE-KMS encryption. This can only be used when you set the value of `sse_algorithm` as `aws:kms`. The default `aws/s3` AWS KMS master key is used if this element is absent while the `sse_algorithm` is `aws:kms`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sse<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The server-side encryption algorithm to use. Valid values are `AES256` and `aws:kms`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">kms_<wbr>master_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS KMS master key ID used for the SSE-KMS encryption. This can only be used when you set the value of `sse_algorithm` as `aws:kms`. The default `aws/s3` AWS KMS master key is used if this element is absent while the `sse_algorithm` is `aws:kms`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sse<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The server-side encryption algorithm to use. Valid values are `AES256` and `aws:kms`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketVersioning
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketVersioning">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketVersioning">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketVersioningArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketVersioningOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketVersioningArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketVersioning.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mfa<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enable MFA delete for either `Change the versioning state of your bucket` or `Permanently delete an object version`. Default is `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mfa<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enable MFA delete for either `Change the versioning state of your bucket` or `Permanently delete an object version`. Default is `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mfa<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enable MFA delete for either `Change the versioning state of your bucket` or `Permanently delete an object version`. Default is `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean which indicates if this criteria is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mfa<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enable MFA delete for either `Change the versioning state of your bucket` or `Permanently delete an object version`. Default is `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketWebsite
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketWebsite">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketWebsite">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketWebsiteArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketWebsiteOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketWebsiteArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketWebsite.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Error<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An absolute path to the document to return in case of a 4XX error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Index<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon S3 returns this index document when requests are made to the root domain or any of the subfolders.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Redirect<wbr>All<wbr>Requests<wbr>To<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A hostname to redirect all website requests for this bucket to. Hostname can optionally be prefixed with a protocol (`http://` or `https://`) to use when redirecting requests. The default is the protocol that is used in the original request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routing<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type">Union<string, ImmutableArray<string>>?</span>
    </dt>
    <dd>{{% md %}}A json array containing [routing rules](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-websiteconfiguration-routingrules.html)
describing redirect behavior and when redirects are applied.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Error<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An absolute path to the document to return in case of a 4XX error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Index<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon S3 returns this index document when requests are made to the root domain or any of the subfolders.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Redirect<wbr>All<wbr>Requests<wbr>To<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A hostname to redirect all website requests for this bucket to. Hostname can optionally be prefixed with a protocol (`http://` or `https://`) to use when redirecting requests. The default is the protocol that is used in the original request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routing<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}A json array containing [routing rules](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-websiteconfiguration-routingrules.html)
describing redirect behavior and when redirects are applied.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">error<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An absolute path to the document to return in case of a 4XX error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">index<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon S3 returns this index document when requests are made to the root domain or any of the subfolders.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">redirect<wbr>All<wbr>Requests<wbr>To<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A hostname to redirect all website requests for this bucket to. Hostname can optionally be prefixed with a protocol (`http://` or `https://`) to use when redirecting requests. The default is the protocol that is used in the original request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routing<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type">string | RoutingRule[]</span>
    </dt>
    <dd>{{% md %}}A json array containing [routing rules](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-websiteconfiguration-routingrules.html)
describing redirect behavior and when redirects are applied.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">error<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An absolute path to the document to return in case of a 4XX error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">index<wbr>Document<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon S3 returns this index document when requests are made to the root domain or any of the subfolders.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">redirect<wbr>All<wbr>Requests<wbr>To<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A hostname to redirect all website requests for this bucket to. Hostname can optionally be prefixed with a protocol (`http://` or `https://`) to use when redirecting requests. The default is the protocol that is used in the original request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routing<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A json array containing [routing rules](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-websiteconfiguration-routingrules.html)
describing redirect behavior and when redirects are applied.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "BucketObject"
block_external_search_index: true
---

Provides a S3 bucket object resource.

## Example Usage

### Encrypting with KMS Key

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const examplekms = new aws.kms.Key("examplekms", {
    deletionWindowInDays: 7,
    description: "KMS key 1",
});
const examplebucket = new aws.s3.Bucket("examplebucket", {
    acl: "private",
});
const examplebucketObject = new aws.s3.BucketObject("examplebucket_object", {
    bucket: examplebucket.id,
    key: "someobject",
    kmsKeyId: examplekms.arn,
    source: new pulumi.asset.FileAsset("index.html"),
});
```

### Server Side Encryption with S3 Default Master Key

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const examplebucket = new aws.s3.Bucket("examplebucket", {
    acl: "private",
});
const examplebucketObject = new aws.s3.BucketObject("examplebucket_object", {
    bucket: examplebucket.id,
    key: "someobject",
    serverSideEncryption: "aws:kms",
    source: new pulumi.asset.FileAsset("index.html"),
});
```

### Server Side Encryption with AWS-Managed Key

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const examplebucket = new aws.s3.Bucket("examplebucket", {
    acl: "private",
});
const examplebucketObject = new aws.s3.BucketObject("examplebucket_object", {
    bucket: examplebucket.id,
    key: "someobject",
    serverSideEncryption: "AES256",
    source: new pulumi.asset.FileAsset("index.html"),
});
```

### S3 Object Lock

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const examplebucket = new aws.s3.Bucket("examplebucket", {
    acl: "private",
    objectLockConfiguration: {
        objectLockEnabled: "Enabled",
    },
    versioning: {
        enabled: true,
    },
});
const examplebucketObject = new aws.s3.BucketObject("examplebucket_object", {
    bucket: examplebucket.id,
    forceDestroy: true,
    key: "someobject",
    objectLockLegalHoldStatus: "ON",
    objectLockMode: "GOVERNANCE",
    objectLockRetainUntilDate: "2021-12-31T23:59:60Z",
    source: new pulumi.asset.FileAsset("important.txt"),
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/s3_bucket_object.html.markdown.



## Create a BucketObject Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketObject">BucketObject</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketObjectArgs">BucketObjectArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BucketObject</span><span class="p">(resource_name, opts=None, </span>acl=None<span class="p">, </span>bucket=None<span class="p">, </span>cache_control=None<span class="p">, </span>content=None<span class="p">, </span>content_base64=None<span class="p">, </span>content_disposition=None<span class="p">, </span>content_encoding=None<span class="p">, </span>content_language=None<span class="p">, </span>content_type=None<span class="p">, </span>etag=None<span class="p">, </span>force_destroy=None<span class="p">, </span>key=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>metadata=None<span class="p">, </span>object_lock_legal_hold_status=None<span class="p">, </span>object_lock_mode=None<span class="p">, </span>object_lock_retain_until_date=None<span class="p">, </span>server_side_encryption=None<span class="p">, </span>source=None<span class="p">, </span>storage_class=None<span class="p">, </span>tags=None<span class="p">, </span>website_redirect=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucketObject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectArgs">BucketObjectArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObject">BucketObject</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObject.html">BucketObject</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectArgs.html">BucketObjectArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Etag<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metadata<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type">AssetOrArchive?</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Etag<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metadata<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type">pulumi.AssetOrArchive</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string | Bucket</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">etag<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metadata<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Asset | pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>control<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>disposition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>encoding<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>language<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">etag<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metadata<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>legal_<wbr>hold_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>retain_<wbr>until_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type">Union[pulumi.Asset, pulumi.Archive]</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website_<wbr>redirect<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## BucketObject Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Etag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metadata<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<span class="property-indicator"></span>
        <span class="property-type">AssetOrArchive?</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Etag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metadata<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<span class="property-indicator"></span>
        <span class="property-type">pulumi.AssetOrArchive</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-"
            title="">etag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">metadata<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-"
            title="">object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-"
            title="">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Asset | pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cache_<wbr>control<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>disposition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>encoding<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>language<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-"
            title="">etag<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">metadata<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-"
            title="">object_<wbr>lock_<wbr>legal_<wbr>hold_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">object_<wbr>lock_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">object_<wbr>lock_<wbr>retain_<wbr>until_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-"
            title="">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<span class="property-indicator"></span>
        <span class="property-type">Union[pulumi.Asset, pulumi.Archive]</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">website_<wbr>redirect<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing BucketObject Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketObjectState">BucketObjectState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketObject">BucketObject</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>acl=None<span class="p">, </span>bucket=None<span class="p">, </span>cache_control=None<span class="p">, </span>content=None<span class="p">, </span>content_base64=None<span class="p">, </span>content_disposition=None<span class="p">, </span>content_encoding=None<span class="p">, </span>content_language=None<span class="p">, </span>content_type=None<span class="p">, </span>etag=None<span class="p">, </span>force_destroy=None<span class="p">, </span>key=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>metadata=None<span class="p">, </span>object_lock_legal_hold_status=None<span class="p">, </span>object_lock_mode=None<span class="p">, </span>object_lock_retain_until_date=None<span class="p">, </span>server_side_encryption=None<span class="p">, </span>source=None<span class="p">, </span>storage_class=None<span class="p">, </span>tags=None<span class="p">, </span>version_id=None<span class="p">, </span>website_redirect=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucketObject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObjectState">BucketObjectState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketObject">BucketObject</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObject.html">BucketObject</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketObjectState.html">BucketObjectState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing BucketObject resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Etag<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metadata<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type">AssetOrArchive?</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acl<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Etag<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metadata<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type">pulumi.AssetOrArchive</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string | Bucket</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache<wbr>Control<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Disposition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Encoding<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Language<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">etag<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metadata<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Legal<wbr>Hold<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Lock<wbr>Retain<wbr>Until<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Asset | pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website<wbr>Redirect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acl<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [canned ACL](https://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl) to apply. Defaults to &#34;private&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put the file in. Alternatively, an [S3 access point](https://docs.aws.amazon.com/AmazonS3/latest/dev/using-access-points.html) ARN can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cache_<wbr>control<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies caching behavior along the request/reply chain Read [w3c cache_control](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.9) for further details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Literal string value to use as the object content, which will be uploaded as UTF-8-encoded text.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded data that will be decoded and uploaded as raw bytes for the object content. This allows safely uploading non-UTF8 binary data, but is recommended only for small content such as the result of the `gzipbase64` function with small text strings. For larger objects, use `source` to stream the content from a disk file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>disposition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies presentational information for the object. Read [w3c content_disposition](http://www.w3.org/Protocols/rfc2616/rfc2616-sec19.html#sec19.5.1) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>encoding<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field. Read [w3c content encoding](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.11) for further information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>language<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The language the content is in e.g. en-US or en-GB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A standard MIME type describing the format of the object data, e.g. application/octet-stream. All Valid MIME Types are valid for this input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">etag<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. The only meaningful value is `${filemd5(&#34;path/to/file&#34;)}` (this provider 0.11.12 or later) or `${md5(file(&#34;path/to/file&#34;))}` (this provider 0.11.11 or earlier).
This attribute is not compatible with KMS encryption, `kms_key_id` or `server_side_encryption = &#34;aws:kms&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow the object to be deleted by removing any legal hold on any object version.
Default is `false`. This value should be set to `true` only if the bucket has S3 object lock enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the object once it is in the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the AWS KMS Key ARN to use for object encryption.
This value is a fully qualified **ARN** of the KMS Key. If using `aws.kms.Key`,
use the exported `arn` attribute:
`kms_key_id = &#34;${aws_kms_key.foo.arn}&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metadata<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A mapping of keys/values to provision metadata (will be automatically prefixed by `x-amz-meta-`, note that only lowercase label are currently supported by the AWS Go API).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>legal_<wbr>hold_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [legal hold](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-legal-holds) status that you want to apply to the specified object. Valid values are `ON` and `OFF`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object lock [retention mode](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-modes) that you want to apply to this object. Valid values are `GOVERNANCE` and `COMPLIANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object_<wbr>lock_<wbr>retain_<wbr>until_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date and time, in [RFC3339 format](https://tools.ietf.org/html/rfc3339#section-5.8), when this object&#39;s object lock will [expire](https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lock-overview.html#object-lock-retention-periods).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies server-side encryption of the object in S3. Valid values are &#34;`AES256`&#34; and &#34;`aws:kms`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type">Union[pulumi.Asset, pulumi.Archive]</span>
    </dt>
    <dd>{{% md %}}The path to a file that will be read and uploaded as raw bytes for the object content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the desired [Storage Class](http://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)
for the object. Can be either &#34;`STANDARD`&#34;, &#34;`REDUCED_REDUNDANCY`&#34;, &#34;`ONEZONE_IA`&#34;, &#34;`INTELLIGENT_TIERING`&#34;, &#34;`GLACIER`&#34;, &#34;`DEEP_ARCHIVE`&#34;, or &#34;`STANDARD_IA`&#34;. Defaults to &#34;`STANDARD`&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique version ID value for the object, if bucket versioning
is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">website_<wbr>redirect<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies a target URL for [website redirect](http://docs.aws.amazon.com/AmazonS3/latest/dev/how-to-page-redirect.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







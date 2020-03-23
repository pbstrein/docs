
---
title: "Trail"
block_external_search_index: true
---

Provides a CloudTrail resource.

> *NOTE:* For a multi-region trail, this resource must be in the home region of the trail.

> *NOTE:* For an organization trail, this resource must be in the master account of the organization.

## Example Usage

### Basic

Enable CloudTrail to capture all compatible management events in region.
For capturing events from services like IAM, `include_global_service_events` must be enabled.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const current = aws.getCallerIdentity();
const foo = new aws.s3.Bucket("foo", {
    forceDestroy: true,
    policy: `{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "AWSCloudTrailAclCheck",
            "Effect": "Allow",
            "Principal": {
              "Service": "cloudtrail.amazonaws.com"
            },
            "Action": "s3:GetBucketAcl",
            "Resource": "arn:aws:s3:::tf-test-trail"
        },
        {
            "Sid": "AWSCloudTrailWrite",
            "Effect": "Allow",
            "Principal": {
              "Service": "cloudtrail.amazonaws.com"
            },
            "Action": "s3:PutObject",
            "Resource": "arn:aws:s3:::tf-test-trail/prefix/AWSLogs/${current.accountId}/*",
            "Condition": {
                "StringEquals": {
                    "s3:x-amz-acl": "bucket-owner-full-control"
                }
            }
        }
    ]
}
`,
});
const foobar = new aws.cloudtrail.Trail("foobar", {
    includeGlobalServiceEvents: false,
    s3BucketName: foo.id,
    s3KeyPrefix: "prefix",
});
```

### Data Event Logging

CloudTrail can log [Data Events](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/logging-management-and-data-events-with-cloudtrail.html#logging-data-events) for certain services such as S3 bucket objects and Lambda function invocations. Additional information about data event configuration can be found in the [CloudTrail API DataResource documentation](https://docs.aws.amazon.com/awscloudtrail/latest/APIReference/API_DataResource.html).

#### Logging All Lambda Function Invocations

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.cloudtrail.Trail("example", {
    eventSelectors: [{
        dataResources: [{
            type: "AWS::Lambda::Function",
            values: ["arn:aws:lambda"],
        }],
        includeManagementEvents: true,
        readWriteType: "All",
    }],
});
```

#### Logging All S3 Bucket Object Events

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.cloudtrail.Trail("example", {
    eventSelectors: [{
        dataResources: [{
            type: "AWS::S3::Object",
            values: ["arn:aws:s3:::"],
        }],
        includeManagementEvents: true,
        readWriteType: "All",
    }],
});
```

#### Logging Individual S3 Bucket Events

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const important_bucket = aws.s3.getBucket({
    bucket: "important-bucket",
});
const example = new aws.cloudtrail.Trail("example", {
    eventSelectors: [{
        dataResources: [{
            type: "AWS::S3::Object",
            // Make sure to append a trailing '/' to your ARN if you want
            // to monitor all objects in a bucket.
            values: [`${important_bucket.arn}/`],
        }],
        includeManagementEvents: true,
        readWriteType: "All",
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cloudtrail.html.markdown.



## Create a Trail Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudtrail/#Trail">Trail</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudtrail/#TrailArgs">TrailArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Trail</span><span class="p">(resource_name, opts=None, </span>cloud_watch_logs_group_arn=None<span class="p">, </span>cloud_watch_logs_role_arn=None<span class="p">, </span>enable_log_file_validation=None<span class="p">, </span>enable_logging=None<span class="p">, </span>event_selectors=None<span class="p">, </span>include_global_service_events=None<span class="p">, </span>is_multi_region_trail=None<span class="p">, </span>is_organization_trail=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>name=None<span class="p">, </span>s3_bucket_name=None<span class="p">, </span>s3_key_prefix=None<span class="p">, </span>sns_topic_name=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTrail<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#TrailArgs">TrailArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#Trail">Trail</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.Trail.html">Trail</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.TrailArgs.html">TrailArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">List&lt;Trail<wbr>Event<wbr>Selector<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">[]Trail<wbr>Event<wbr>Selector</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">Trail<wbr>Event<wbr>Selector[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cloud_<wbr>watch_<wbr>logs_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloud_<wbr>watch_<wbr>logs_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>log_<wbr>file_<wbr>validation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>logging<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event_<wbr>selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">List[Trail<wbr>Event<wbr>Selector]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include_<wbr>global_<wbr>service_<wbr>events<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is_<wbr>multi_<wbr>region_<wbr>trail<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is_<wbr>organization_<wbr>trail<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>topic_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Trail Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">List&lt;Trail<wbr>Event<wbr>Selector&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Home<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">[]Trail<wbr>Event<wbr>Selector</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Home<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-"
            title="">event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">Trail<wbr>Event<wbr>Selector[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-"
            title="">home<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloud_<wbr>watch_<wbr>logs_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cloud_<wbr>watch_<wbr>logs_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>log_<wbr>file_<wbr>validation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>logging<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-"
            title="">event_<wbr>selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">List[Trail<wbr>Event<wbr>Selector]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-"
            title="">home_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">include_<wbr>global_<wbr>service_<wbr>events<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">is_<wbr>multi_<wbr>region_<wbr>trail<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">is_<wbr>organization_<wbr>trail<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns_<wbr>topic_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Trail Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudtrail/#TrailState">TrailState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudtrail/#Trail">Trail</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>cloud_watch_logs_group_arn=None<span class="p">, </span>cloud_watch_logs_role_arn=None<span class="p">, </span>enable_log_file_validation=None<span class="p">, </span>enable_logging=None<span class="p">, </span>event_selectors=None<span class="p">, </span>home_region=None<span class="p">, </span>include_global_service_events=None<span class="p">, </span>is_multi_region_trail=None<span class="p">, </span>is_organization_trail=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>name=None<span class="p">, </span>s3_bucket_name=None<span class="p">, </span>s3_key_prefix=None<span class="p">, </span>sns_topic_name=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTrail<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#TrailState">TrailState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#Trail">Trail</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.Trail.html">Trail</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.TrailState.html">TrailState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Trail resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">List&lt;Trail<wbr>Event<wbr>Selector<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Home<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">[]Trail<wbr>Event<wbr>Selector</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Home<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloud<wbr>Watch<wbr>Logs<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloud<wbr>Watch<wbr>Logs<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Log<wbr>File<wbr>Validation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event<wbr>Selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">Trail<wbr>Event<wbr>Selector[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">home<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Global<wbr>Service<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is<wbr>Multi<wbr>Region<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is<wbr>Organization<wbr>Trail<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Topic<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloud_<wbr>watch_<wbr>logs_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies a log group name using an Amazon Resource Name (ARN),
that represents the log group to which CloudTrail logs will be delivered.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloud_<wbr>watch_<wbr>logs_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the role for the CloudWatch Logs
endpoint to assume to write to a user’s log group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>log_<wbr>file_<wbr>validation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether log file integrity validation is enabled.
Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>logging<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables logging for the trail. Defaults to `true`.
Setting this to `false` will pause logging.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">event_<wbr>selectors<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselector">List[Trail<wbr>Event<wbr>Selector]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an event selector for enabling data event logging. Fields documented below. Please note the [CloudTrail limits](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/WhatIsCloudTrail-Limits.html) when configuring these.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">home_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region in which the trail was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include_<wbr>global_<wbr>service_<wbr>events<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is publishing events
from global services such as IAM to the log files. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is_<wbr>multi_<wbr>region_<wbr>trail<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is created in the current
region or in all regions. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is_<wbr>organization_<wbr>trail<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the trail is an AWS Organizations trail. Organization trails log events for the master account and all member accounts. Can only be created in the organization master account. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the KMS key ARN to use to encrypt the logs delivered by CloudTrail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the S3 bucket designated for publishing log files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 key prefix that follows
the name of the bucket you have designated for log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>topic_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the name of the Amazon SNS topic
defined for notification of log file delivery.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the trail
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### TrailEventSelector
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TrailEventSelector">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TrailEventSelector">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#TrailEventSelectorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#TrailEventSelectorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.TrailEventSelectorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.TrailEventSelector.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Data<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselectordataresource">List&lt;Trail<wbr>Event<wbr>Selector<wbr>Data<wbr>Resource<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies logging data events. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Management<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specify if you want your event selector to include management events for your trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Write<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify if you want your trail to log read-only events, write-only events, or all. By default, the value is All. You can specify only the following value: &#34;ReadOnly&#34;, &#34;WriteOnly&#34;, &#34;All&#34;. Defaults to `All`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Data<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselectordataresource">[]Trail<wbr>Event<wbr>Selector<wbr>Data<wbr>Resource</a></span>
    </dt>
    <dd>{{% md %}}Specifies logging data events. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Management<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specify if you want your event selector to include management events for your trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Write<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify if you want your trail to log read-only events, write-only events, or all. By default, the value is All. You can specify only the following value: &#34;ReadOnly&#34;, &#34;WriteOnly&#34;, &#34;All&#34;. Defaults to `All`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">data<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselectordataresource">Trail<wbr>Event<wbr>Selector<wbr>Data<wbr>Resource[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies logging data events. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Management<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specify if you want your event selector to include management events for your trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Write<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify if you want your trail to log read-only events, write-only events, or all. By default, the value is All. You can specify only the following value: &#34;ReadOnly&#34;, &#34;WriteOnly&#34;, &#34;All&#34;. Defaults to `All`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">data<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#traileventselectordataresource">List[Trail<wbr>Event<wbr>Selector<wbr>Data<wbr>Resource]</a></span>
    </dt>
    <dd>{{% md %}}Specifies logging data events. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Management<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specify if you want your event selector to include management events for your trail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Write<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify if you want your trail to log read-only events, write-only events, or all. By default, the value is All. You can specify only the following value: &#34;ReadOnly&#34;, &#34;WriteOnly&#34;, &#34;All&#34;. Defaults to `All`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TrailEventSelectorDataResource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TrailEventSelectorDataResource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TrailEventSelectorDataResource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#TrailEventSelectorDataResourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudtrail?tab=doc#TrailEventSelectorDataResourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.TrailEventSelectorDataResourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudtrail.TrailEventSelectorDataResource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource type in which you want to log data events. You can specify only the following value: &#34;AWS::S3::Object&#34;, &#34;AWS::Lambda::Function&#34;
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of ARN for the specified S3 buckets and object prefixes..
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource type in which you want to log data events. You can specify only the following value: &#34;AWS::S3::Object&#34;, &#34;AWS::Lambda::Function&#34;
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of ARN for the specified S3 buckets and object prefixes..
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The resource type in which you want to log data events. You can specify only the following value: &#34;AWS::S3::Object&#34;, &#34;AWS::Lambda::Function&#34;
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of ARN for the specified S3 buckets and object prefixes..
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The resource type in which you want to log data events. You can specify only the following value: &#34;AWS::S3::Object&#34;, &#34;AWS::Lambda::Function&#34;
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of ARN for the specified S3 buckets and object prefixes..
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








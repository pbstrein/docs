
---
title: "BucketNotification"
block_external_search_index: true
---

Manages a S3 Bucket Notification Configuration. For additional information, see the [Configuring S3 Event Notifications section in the Amazon S3 Developer Guide](https://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html).

> **NOTE:** S3 Buckets only support a single notification configuration. Declaring multiple `aws.s3.BucketNotification` resources to the same S3 Bucket will cause a perpetual difference in configuration. See the example "Trigger multiple Lambda functions" for an option.

## Example Usage

### Add notification configuration to SNS Topic

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("bucket", {});
const topic = new aws.sns.Topic("topic", {
    policy: pulumi.interpolate`{
    "Version":"2012-10-17",
    "Statement":[{
        "Effect": "Allow",
        "Principal": {"AWS":"*"},
        "Action": "SNS:Publish",
        "Resource": "arn:aws:sns:*:*:s3-event-notification-topic",
        "Condition":{
            "ArnLike":{"aws:SourceArn":"${bucket.arn}"}
        }
    }]
}
`,
});
const bucketNotification = new aws.s3.BucketNotification("bucket_notification", {
    bucket: bucket.id,
    topics: [{
        events: ["s3:ObjectCreated:*"],
        filterSuffix: ".log",
        topicArn: topic.arn,
    }],
});
```

### Add notification configuration to SQS Queue

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("bucket", {});
const queue = new aws.sqs.Queue("queue", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "sqs:SendMessage",
	  "Resource": "arn:aws:sqs:*:*:s3-event-notification-queue",
      "Condition": {
        "ArnEquals": { "aws:SourceArn": "${bucket.arn}" }
      }
    }
  ]
}
`,
});
const bucketNotification = new aws.s3.BucketNotification("bucket_notification", {
    bucket: bucket.id,
    queues: [{
        events: ["s3:ObjectCreated:*"],
        filterSuffix: ".log",
        queueArn: queue.arn,
    }],
});
```

### Add multiple notification configurations to SQS Queue

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("bucket", {});
const queue = new aws.sqs.Queue("queue", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "sqs:SendMessage",
	  "Resource": "arn:aws:sqs:*:*:s3-event-notification-queue",
      "Condition": {
        "ArnEquals": { "aws:SourceArn": "${bucket.arn}" }
      }
    }
  ]
}
`,
});
const bucketNotification = new aws.s3.BucketNotification("bucket_notification", {
    bucket: bucket.id,
    queues: [
        {
            events: ["s3:ObjectCreated:*"],
            filterPrefix: "images/",
            id: "image-upload-event",
            queueArn: queue.arn,
        },
        {
            events: ["s3:ObjectCreated:*"],
            filterPrefix: "videos/",
            id: "video-upload-event",
            queueArn: queue.arn,
        },
    ],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/s3_bucket_notification.html.markdown.



## Create a BucketNotification Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketNotification">BucketNotification</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketNotificationArgs">BucketNotificationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BucketNotification</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>lambda_functions=None<span class="p">, </span>queues=None<span class="p">, </span>topics=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucketNotification<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationArgs">BucketNotificationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotification">BucketNotification</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotification.html">BucketNotification</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationArgs.html">BucketNotificationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">List&lt;Bucket<wbr>Notification<wbr>Lambda<wbr>Function<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">List&lt;Bucket<wbr>Notification<wbr>Queue<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">List&lt;Bucket<wbr>Notification<wbr>Topic<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">[]Bucket<wbr>Notification<wbr>Lambda<wbr>Function</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">[]Bucket<wbr>Notification<wbr>Queue</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">[]Bucket<wbr>Notification<wbr>Topic</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">Bucket<wbr>Notification<wbr>Lambda<wbr>Function[]?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">Bucket<wbr>Notification<wbr>Queue[]?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">Bucket<wbr>Notification<wbr>Topic[]?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">List[Bucket<wbr>Notification<wbr>Lambda<wbr>Function]</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">List[Bucket<wbr>Notification<wbr>Queue]</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">List[Bucket<wbr>Notification<wbr>Topic]</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## BucketNotification Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">List&lt;Bucket<wbr>Notification<wbr>Lambda<wbr>Function&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">List&lt;Bucket<wbr>Notification<wbr>Queue&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">List&lt;Bucket<wbr>Notification<wbr>Topic&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">[]Bucket<wbr>Notification<wbr>Lambda<wbr>Function</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">[]Bucket<wbr>Notification<wbr>Queue</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">[]Bucket<wbr>Notification<wbr>Topic</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">Bucket<wbr>Notification<wbr>Lambda<wbr>Function[]?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">Bucket<wbr>Notification<wbr>Queue[]?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">Bucket<wbr>Notification<wbr>Topic[]?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">List[Bucket<wbr>Notification<wbr>Lambda<wbr>Function]</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">List[Bucket<wbr>Notification<wbr>Queue]</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">List[Bucket<wbr>Notification<wbr>Topic]</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing BucketNotification Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketNotificationState">BucketNotificationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#BucketNotification">BucketNotification</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>lambda_functions=None<span class="p">, </span>queues=None<span class="p">, </span>topics=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucketNotification<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationState">BucketNotificationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotification">BucketNotification</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotification.html">BucketNotification</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationState.html">BucketNotificationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing BucketNotification resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">List&lt;Bucket<wbr>Notification<wbr>Lambda<wbr>Function<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">List&lt;Bucket<wbr>Notification<wbr>Queue<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">List&lt;Bucket<wbr>Notification<wbr>Topic<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">[]Bucket<wbr>Notification<wbr>Lambda<wbr>Function</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">[]Bucket<wbr>Notification<wbr>Queue</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">[]Bucket<wbr>Notification<wbr>Topic</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">Bucket<wbr>Notification<wbr>Lambda<wbr>Function[]?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">Bucket<wbr>Notification<wbr>Queue[]?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">Bucket<wbr>Notification<wbr>Topic[]?</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket to put notification configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>functions<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationlambdafunction">List[Bucket<wbr>Notification<wbr>Lambda<wbr>Function]</a></span>
    </dt>
    <dd>{{% md %}}Used to configure notifications to a Lambda Function (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">queues<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationqueue">List[Bucket<wbr>Notification<wbr>Queue]</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SQS Queue (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topics<span class="property-indicator"></span>
        <span class="property-type"><a href="#bucketnotificationtopic">List[Bucket<wbr>Notification<wbr>Topic]</a></span>
    </dt>
    <dd>{{% md %}}The notification configuration to SNS Topic (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### BucketNotificationLambdaFunction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketNotificationLambdaFunction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketNotificationLambdaFunction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationLambdaFunctionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationLambdaFunctionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationLambdaFunctionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationLambdaFunction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Events<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon Lambda function ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Events<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon Lambda function ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">events<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon Lambda function ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">events<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>function_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon Lambda function ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketNotificationQueue
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketNotificationQueue">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketNotificationQueue">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationQueueArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationQueueOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationQueueArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationQueue.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Events<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Queue<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SQS queue ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Events<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Queue<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SQS queue ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">events<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">queue<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SQS queue ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">events<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">queue<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SQS queue ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BucketNotificationTopic
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BucketNotificationTopic">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BucketNotificationTopic">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationTopicArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#BucketNotificationTopicOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationTopicArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.BucketNotificationTopic.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Events<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SNS topic ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Events<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SNS topic ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">events<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SNS topic ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">events<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies [event](http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html#notification-how-to-event-types-and-destinations) for which to send notifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies object key name prefix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies object key name suffix.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies unique identifier for each of the notification configurations.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies Amazon SNS topic ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








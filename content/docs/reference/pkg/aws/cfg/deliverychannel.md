
---
title: "DeliveryChannel"
block_external_search_index: true
---

Provides an AWS Config Delivery Channel.

> **Note:** Delivery Channel requires a [Configuration Recorder](https://www.terraform.io/docs/providers/aws/r/config_configuration_recorder.html) to be present. Use of `depends_on` (as shown below) is recommended to avoid race conditions.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("b", {
    forceDestroy: true,
});
const role = new aws.iam.Role("r", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "config.amazonaws.com"
      },
      "Effect": "Allow",
      "Sid": ""
    }
  ]
}
`,
});
const fooRecorder = new aws.cfg.Recorder("foo", {
    roleArn: role.arn,
});
const fooDeliveryChannel = new aws.cfg.DeliveryChannel("foo", {
    s3BucketName: bucket.bucket,
}, {dependsOn: [fooRecorder]});
const rolePolicy = new aws.iam.RolePolicy("p", {
    policy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "s3:*"
      ],
      "Effect": "Allow",
      "Resource": [
        "${bucket.arn}",
        "${bucket.arn}/*"
      ]
    }
  ]
}
`,
    role: role.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/config_delivery_channel.html.markdown.



## Create a DeliveryChannel Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#DeliveryChannel">DeliveryChannel</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#DeliveryChannelArgs">DeliveryChannelArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DeliveryChannel</span><span class="p">(resource_name, opts=None, </span>name=None<span class="p">, </span>s3_bucket_name=None<span class="p">, </span>s3_key_prefix=None<span class="p">, </span>snapshot_delivery_properties=None<span class="p">, </span>sns_topic_arn=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDeliveryChannel<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#DeliveryChannelArgs">DeliveryChannelArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#DeliveryChannel">DeliveryChannel</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.DeliveryChannel.html">DeliveryChannel</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.DeliveryChannelArgs.html">DeliveryChannelArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">*Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties?</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>delivery_<wbr>properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Dict[Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties]</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## DeliveryChannel Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties?</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">*Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties?</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>delivery_<wbr>properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Dict[Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties]</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing DeliveryChannel Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#DeliveryChannelState">DeliveryChannelState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#DeliveryChannel">DeliveryChannel</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>name=None<span class="p">, </span>s3_bucket_name=None<span class="p">, </span>s3_key_prefix=None<span class="p">, </span>snapshot_delivery_properties=None<span class="p">, </span>sns_topic_arn=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDeliveryChannel<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#DeliveryChannelState">DeliveryChannelState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#DeliveryChannel">DeliveryChannel</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.DeliveryChannel.html">DeliveryChannel</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.DeliveryChannelState.html">DeliveryChannelState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing DeliveryChannel resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">*Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Delivery<wbr>Properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties?</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the delivery channel. Defaults to `default`. Changing it recreates the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket used to store the configuration history.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The prefix for the specified S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>delivery_<wbr>properties<span class="property-indicator"></span>
        <span class="property-type"><a href="#deliverychannelsnapshotdeliveryproperties">Dict[Delivery<wbr>Channel<wbr>Snapshot<wbr>Delivery<wbr>Properties]</a></span>
    </dt>
    <dd>{{% md %}}Options for how AWS Config delivers configuration snapshots. See below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic that AWS Config delivers notifications to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DeliveryChannelSnapshotDeliveryProperties
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeliveryChannelSnapshotDeliveryProperties">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeliveryChannelSnapshotDeliveryProperties">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#DeliveryChannelSnapshotDeliveryPropertiesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#DeliveryChannelSnapshotDeliveryPropertiesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.DeliveryChannelSnapshotDeliveryPropertiesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.DeliveryChannelSnapshotDeliveryProperties.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- The frequency with which AWS Config recurringly delivers configuration snapshots.
e.g. `One_Hour` or `Three_Hours`.
Valid values are listed [here](https://docs.aws.amazon.com/config/latest/APIReference/API_ConfigSnapshotDeliveryProperties.html#API_ConfigSnapshotDeliveryProperties_Contents).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}- The frequency with which AWS Config recurringly delivers configuration snapshots.
e.g. `One_Hour` or `Three_Hours`.
Valid values are listed [here](https://docs.aws.amazon.com/config/latest/APIReference/API_ConfigSnapshotDeliveryProperties.html#API_ConfigSnapshotDeliveryProperties_Contents).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delivery<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- The frequency with which AWS Config recurringly delivers configuration snapshots.
e.g. `One_Hour` or `Three_Hours`.
Valid values are listed [here](https://docs.aws.amazon.com/config/latest/APIReference/API_ConfigSnapshotDeliveryProperties.html#API_ConfigSnapshotDeliveryProperties_Contents).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delivery<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}- The frequency with which AWS Config recurringly delivers configuration snapshots.
e.g. `One_Hour` or `Three_Hours`.
Valid values are listed [here](https://docs.aws.amazon.com/config/latest/APIReference/API_ConfigSnapshotDeliveryProperties.html#API_ConfigSnapshotDeliveryProperties_Contents).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








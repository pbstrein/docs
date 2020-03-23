
---
title: "SmsPreferences"
block_external_search_index: true
---

Provides a way to set SNS SMS preferences.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const updateSmsPrefs = new aws.sns.SmsPreferences("update_sms_prefs", {});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/sns_sms_preferences.html.markdown.



## Create a SmsPreferences Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#SmsPreferences">SmsPreferences</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#SmsPreferencesArgs">SmsPreferencesArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SmsPreferences</span><span class="p">(resource_name, opts=None, </span>default_sender_id=None<span class="p">, </span>default_sms_type=None<span class="p">, </span>delivery_status_iam_role_arn=None<span class="p">, </span>delivery_status_success_sampling_rate=None<span class="p">, </span>monthly_spend_limit=None<span class="p">, </span>usage_report_s3_bucket=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSmsPreferences<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#SmsPreferencesArgs">SmsPreferencesArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#SmsPreferences">SmsPreferences</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.SmsPreferences.html">SmsPreferences</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.SmsPreferencesArgs.html">SmsPreferencesArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default_<wbr>sender_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>sms_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery_<wbr>status_<wbr>iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery_<wbr>status_<wbr>success_<wbr>sampling_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monthly_<wbr>spend_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">usage_<wbr>report_<wbr>s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SmsPreferences Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-"
            title="">Delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-"
            title="">Delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-"
            title="">delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-"
            title="">usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">default_<wbr>sender_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>sms_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-"
            title="">delivery_<wbr>status_<wbr>iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">delivery_<wbr>status_<wbr>success_<wbr>sampling_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monthly_<wbr>spend_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-"
            title="">usage_<wbr>report_<wbr>s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SmsPreferences Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#SmsPreferencesState">SmsPreferencesState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#SmsPreferences">SmsPreferences</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>default_sender_id=None<span class="p">, </span>default_sms_type=None<span class="p">, </span>delivery_status_iam_role_arn=None<span class="p">, </span>delivery_status_success_sampling_rate=None<span class="p">, </span>monthly_spend_limit=None<span class="p">, </span>usage_report_s3_bucket=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSmsPreferences<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#SmsPreferencesState">SmsPreferencesState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#SmsPreferences">SmsPreferences</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.SmsPreferences.html">SmsPreferences</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.SmsPreferencesState.html">SmsPreferencesState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SmsPreferences resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default<wbr>Sender<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Sms<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery<wbr>Status<wbr>Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery<wbr>Status<wbr>Success<wbr>Sampling<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monthly<wbr>Spend<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">usage<wbr>Report<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default_<wbr>sender_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string, such as your business brand, that is displayed as the sender on the receiving device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>sms_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of SMS message that you will send by default. Possible values are: Promotional, Transactional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery_<wbr>status_<wbr>iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role that allows Amazon SNS to write logs about SMS deliveries in CloudWatch Logs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery_<wbr>status_<wbr>success_<wbr>sampling_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The percentage of successful SMS deliveries for which Amazon SNS will write logs in CloudWatch Logs. The value must be between 0 and 100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monthly_<wbr>spend_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum amount in USD that you are willing to spend each month to send SMS messages.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">usage_<wbr>report_<wbr>s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket to receive daily SMS usage reports from Amazon SNS.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







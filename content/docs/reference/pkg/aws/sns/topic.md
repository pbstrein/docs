
---
title: "Topic"
block_external_search_index: true
---

Provides an SNS topic resource

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const userUpdates = new aws.sns.Topic("user_updates", {});
```

## Example with Delivery Policy

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const userUpdates = new aws.sns.Topic("user_updates", {
    deliveryPolicy: `{
  "http": {
    "defaultHealthyRetryPolicy": {
      "minDelayTarget": 20,
      "maxDelayTarget": 20,
      "numRetries": 3,
      "numMaxDelayRetries": 0,
      "numNoDelayRetries": 0,
      "numMinDelayRetries": 0,
      "backoffFunction": "linear"
    },
    "disableSubscriptionOverrides": false,
    "defaultThrottlePolicy": {
      "maxReceivesPerSecond": 1
    }
  }
}
`,
});
```

## Example with Server-side encryption (SSE)

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const userUpdates = new aws.sns.Topic("user_updates", {
    kmsMasterKeyId: "alias/aws/sns",
});
```

## Message Delivery Status Arguments

The `<endpoint>_success_feedback_role_arn` and `<endpoint>_failure_feedback_role_arn` arguments are used to give Amazon SNS write access to use CloudWatch Logs on your behalf. The `<endpoint>_success_feedback_sample_rate` argument is for specifying the sample rate percentage (0-100) of successfully delivered messages. After you configure the  `<endpoint>_failure_feedback_role_arn` argument, then all failed message deliveries generate CloudWatch Logs.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/sns_topic.html.markdown.



## Create a Topic Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#Topic">Topic</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#TopicArgs">TopicArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Topic</span><span class="p">(resource_name, opts=None, </span>application_failure_feedback_role_arn=None<span class="p">, </span>application_success_feedback_role_arn=None<span class="p">, </span>application_success_feedback_sample_rate=None<span class="p">, </span>delivery_policy=None<span class="p">, </span>display_name=None<span class="p">, </span>http_failure_feedback_role_arn=None<span class="p">, </span>http_success_feedback_role_arn=None<span class="p">, </span>http_success_feedback_sample_rate=None<span class="p">, </span>kms_master_key_id=None<span class="p">, </span>lambda_failure_feedback_role_arn=None<span class="p">, </span>lambda_success_feedback_role_arn=None<span class="p">, </span>lambda_success_feedback_sample_rate=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>policy=None<span class="p">, </span>sqs_failure_feedback_role_arn=None<span class="p">, </span>sqs_success_feedback_role_arn=None<span class="p">, </span>sqs_success_feedback_sample_rate=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTopic<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#TopicArgs">TopicArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#Topic">Topic</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.Topic.html">Topic</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.TopicArgs.html">TopicArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">application_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>master_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Topic Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">ARN</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-"
            title="">delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">application_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">application_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">application_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-"
            title="">delivery_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-"
            title="">display_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>master_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-"
            title="">sqs_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Topic Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#TopicState">TopicState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/sns/#Topic">Topic</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>application_failure_feedback_role_arn=None<span class="p">, </span>application_success_feedback_role_arn=None<span class="p">, </span>application_success_feedback_sample_rate=None<span class="p">, </span>arn=None<span class="p">, </span>delivery_policy=None<span class="p">, </span>display_name=None<span class="p">, </span>http_failure_feedback_role_arn=None<span class="p">, </span>http_success_feedback_role_arn=None<span class="p">, </span>http_success_feedback_sample_rate=None<span class="p">, </span>kms_master_key_id=None<span class="p">, </span>lambda_failure_feedback_role_arn=None<span class="p">, </span>lambda_success_feedback_role_arn=None<span class="p">, </span>lambda_success_feedback_sample_rate=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>policy=None<span class="p">, </span>sqs_failure_feedback_role_arn=None<span class="p">, </span>sqs_success_feedback_role_arn=None<span class="p">, </span>sqs_success_feedback_sample_rate=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTopic<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#TopicState">TopicState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/sns?tab=doc#Topic">Topic</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.Topic.html">Topic</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Sns.TopicState.html">TopicState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Topic resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">application<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">ARN?</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Master<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<wbr>Failure<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<wbr>Success<wbr>Feedback<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs<wbr>Success<wbr>Feedback<wbr>Sample<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">application_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">application_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic, as a more obvious property (clone of id)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delivery_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SNS delivery policy. More on [AWS documentation](https://docs.aws.amazon.com/sns/latest/dg/DeliveryPolicies.html)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display name for the SNS topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>master_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of an AWS-managed customer master key (CMK) for Amazon SNS or a custom CMK. For more information, see [Key Terms](https://docs.aws.amazon.com/sns/latest/dg/sns-server-side-encryption.html#sse-key-terms)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The friendly name for the SNS topic. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs_<wbr>failure_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role for failure feedback
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs_<wbr>success_<wbr>feedback_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM role permitted to receive success feedback for this topic
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sqs_<wbr>success_<wbr>feedback_<wbr>sample_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Percentage of success to sample
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







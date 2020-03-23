
---
title: "Policy"
block_external_search_index: true
---

Provides an AutoScaling Scaling Policy resource.

> **NOTE:** You may want to omit `desired_capacity` attribute from attached `aws.autoscaling.Group`
when using autoscaling policies. It's good practice to pick either
[manual](https://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-manual-scaling.html)
or [dynamic](https://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-scale-based-on-demand.html)
(policy-based) scaling.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bar = new aws.autoscaling.Group("bar", {
    availabilityZones: ["us-east-1a"],
    forceDelete: true,
    healthCheckGracePeriod: 300,
    healthCheckType: "ELB",
    launchConfiguration: aws_launch_configuration_foo.name,
    maxSize: 5,
    minSize: 2,
});
const bat = new aws.autoscaling.Policy("bat", {
    adjustmentType: "ChangeInCapacity",
    autoscalingGroupName: bar.name,
    cooldown: 300,
    scalingAdjustment: 4,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/autoscaling_policy.html.markdown.



## Create a Policy Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#Policy">Policy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#PolicyArgs">PolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Policy</span><span class="p">(resource_name, opts=None, </span>adjustment_type=None<span class="p">, </span>autoscaling_group_name=None<span class="p">, </span>cooldown=None<span class="p">, </span>estimated_instance_warmup=None<span class="p">, </span>metric_aggregation_type=None<span class="p">, </span>min_adjustment_magnitude=None<span class="p">, </span>name=None<span class="p">, </span>policy_type=None<span class="p">, </span>scaling_adjustment=None<span class="p">, </span>step_adjustments=None<span class="p">, </span>target_tracking_configuration=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyArgs">PolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#Policy">Policy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.Policy.html">Policy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyArgs.html">PolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cooldown<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">List&lt;Policy<wbr>Step<wbr>Adjustment<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cooldown<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">[]Policy<wbr>Step<wbr>Adjustment</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">*Policy<wbr>Target<wbr>Tracking<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cooldown<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">Policy<wbr>Step<wbr>Adjustment[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Policy<wbr>Target<wbr>Tracking<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">adjustment_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">autoscaling_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cooldown<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">estimated_<wbr>instance_<wbr>warmup<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>aggregation_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min_<wbr>adjustment_<wbr>magnitude<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scaling_<wbr>adjustment<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">step_<wbr>adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">List[Policy<wbr>Step<wbr>Adjustment]</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>tracking_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Dict[Policy<wbr>Target<wbr>Tracking<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Policy Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cooldown<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">List&lt;Policy<wbr>Step<wbr>Adjustment&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Policy<wbr>Target<wbr>Tracking<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cooldown<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">[]Policy<wbr>Step<wbr>Adjustment</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">*Policy<wbr>Target<wbr>Tracking<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cooldown<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-"
            title="">estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-"
            title="">step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">Policy<wbr>Step<wbr>Adjustment[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Policy<wbr>Target<wbr>Tracking<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">adjustment_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cooldown<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-"
            title="">estimated_<wbr>instance_<wbr>warmup<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric_<wbr>aggregation_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">min_<wbr>adjustment_<wbr>magnitude<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">scaling_<wbr>adjustment<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-"
            title="">step_<wbr>adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">List[Policy<wbr>Step<wbr>Adjustment]</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>tracking_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Dict[Policy<wbr>Target<wbr>Tracking<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Policy Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#PolicyState">PolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#Policy">Policy</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>adjustment_type=None<span class="p">, </span>arn=None<span class="p">, </span>autoscaling_group_name=None<span class="p">, </span>cooldown=None<span class="p">, </span>estimated_instance_warmup=None<span class="p">, </span>metric_aggregation_type=None<span class="p">, </span>min_adjustment_magnitude=None<span class="p">, </span>name=None<span class="p">, </span>policy_type=None<span class="p">, </span>scaling_adjustment=None<span class="p">, </span>step_adjustments=None<span class="p">, </span>target_tracking_configuration=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyState">PolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#Policy">Policy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.Policy.html">Policy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyState.html">PolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Policy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cooldown<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">List&lt;Policy<wbr>Step<wbr>Adjustment<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cooldown<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">[]Policy<wbr>Step<wbr>Adjustment</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">*Policy<wbr>Target<wbr>Tracking<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">adjustment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cooldown<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">estimated<wbr>Instance<wbr>Warmup<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Aggregation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Adjustment<wbr>Magnitude<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">step<wbr>Adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">Policy<wbr>Step<wbr>Adjustment[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Tracking<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Policy<wbr>Target<wbr>Tracking<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">adjustment_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether the adjustment is an absolute number or a percentage of the current capacity. Valid values are `ChangeInCapacity`, `ExactCapacity`, and `PercentChangeInCapacity`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the scaling policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the autoscaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cooldown<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, after a scaling activity completes and before the next scaling activity can start.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">estimated_<wbr>instance_<wbr>warmup<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The estimated time, in seconds, until a newly launched instance will contribute CloudWatch metrics. Without a value, AWS will default to the group&#39;s specified cooldown period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>aggregation_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The aggregation type for the policy&#39;s metrics. Valid values are &#34;Minimum&#34;, &#34;Maximum&#34;, and &#34;Average&#34;. Without a value, AWS will treat the aggregation type as &#34;Average&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min_<wbr>adjustment_<wbr>magnitude<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The policy type, either &#34;SimpleScaling&#34;, &#34;StepScaling&#34; or &#34;TargetTrackingScaling&#34;. If this value isn&#39;t provided, AWS will default to &#34;SimpleScaling.&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scaling_<wbr>adjustment<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">step_<wbr>adjustments<span class="property-indicator"></span>
        <span class="property-type"><a href="#policystepadjustment">List[Policy<wbr>Step<wbr>Adjustment]</a></span>
    </dt>
    <dd>{{% md %}}A set of adjustments that manage
group scaling. These have the following structure:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>tracking_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfiguration">Dict[Policy<wbr>Target<wbr>Tracking<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}A target tracking policy. These have the following structure:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### PolicyStepAdjustment
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PolicyStepAdjustment">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PolicyStepAdjustment">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyStepAdjustmentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyStepAdjustmentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyStepAdjustmentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyStepAdjustment.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Metric<wbr>Interval<wbr>Lower<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The lower bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Interval<wbr>Upper<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The upper bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity. The upper bound
must be greater than the lower bound.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Metric<wbr>Interval<wbr>Lower<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The lower bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Interval<wbr>Upper<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The upper bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity. The upper bound
must be greater than the lower bound.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">metric<wbr>Interval<wbr>Lower<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The lower bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Interval<wbr>Upper<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The upper bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity. The upper bound
must be greater than the lower bound.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scaling<wbr>Adjustment<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">metric<wbr>Interval<wbr>Lower<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The lower bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Interval<wbr>Upper<wbr>Bound<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The upper bound for the
difference between the alarm threshold and the CloudWatch metric.
Without a value, AWS will treat this bound as infinity. The upper bound
must be greater than the lower bound.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scaling_<wbr>adjustment<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of members by which to
scale, when the adjustment bounds are breached. A positive value scales
up. A negative value scales down.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PolicyTargetTrackingConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PolicyTargetTrackingConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PolicyTargetTrackingConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Customized<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecification">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A customized metric. Conflicts with `predefined_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Scale<wbr>In<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether scale in by the target tracking policy is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Predefined<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationpredefinedmetricspecification">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Predefined<wbr>Metric<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A predefined metric. Conflicts with `customized_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">double</span>
    </dt>
    <dd>{{% md %}}The target value for the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Customized<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecification">*Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}A customized metric. Conflicts with `predefined_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Scale<wbr>In<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether scale in by the target tracking policy is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Predefined<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationpredefinedmetricspecification">*Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Predefined<wbr>Metric<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}A predefined metric. Conflicts with `customized_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">float64</span>
    </dt>
    <dd>{{% md %}}The target value for the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">customized<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecification">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}A customized metric. Conflicts with `predefined_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Scale<wbr>In<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether scale in by the target tracking policy is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">predefined<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationpredefinedmetricspecification">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Predefined<wbr>Metric<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}A predefined metric. Conflicts with `customized_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The target value for the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">customized<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecification">Dict[Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}A customized metric. Conflicts with `predefined_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Scale<wbr>In<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether scale in by the target tracking policy is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">predefined<wbr>Metric<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationpredefinedmetricspecification">Dict[Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Predefined<wbr>Metric<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}A predefined metric. Conflicts with `customized_metric_specification`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The target value for the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PolicyTargetTrackingConfigurationCustomizedMetricSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PolicyTargetTrackingConfigurationCustomizedMetricSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PolicyTargetTrackingConfigurationCustomizedMetricSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationCustomizedMetricSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationCustomizedMetricSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationCustomizedMetricSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationCustomizedMetricSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Metric<wbr>Dimensions<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecificationmetricdimension">List&lt;Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification<wbr>Metric<wbr>Dimension<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The dimensions of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The namespace of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Statistic<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The statistic of the metric.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit of the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Metric<wbr>Dimensions<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecificationmetricdimension">[]Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification<wbr>Metric<wbr>Dimension</a></span>
    </dt>
    <dd>{{% md %}}The dimensions of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The namespace of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Statistic<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The statistic of the metric.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The unit of the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">metric<wbr>Dimensions<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecificationmetricdimension">Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification<wbr>Metric<wbr>Dimension[]?</a></span>
    </dt>
    <dd>{{% md %}}The dimensions of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The namespace of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">statistic<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The statistic of the metric.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit of the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">metric<wbr>Dimensions<span class="property-indicator"></span>
        <span class="property-type"><a href="#policytargettrackingconfigurationcustomizedmetricspecificationmetricdimension">List[Policy<wbr>Target<wbr>Tracking<wbr>Configuration<wbr>Customized<wbr>Metric<wbr>Specification<wbr>Metric<wbr>Dimension]</a></span>
    </dt>
    <dd>{{% md %}}The dimensions of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace of the metric.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The statistic of the metric.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unit of the metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimension
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimension">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimension">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimensionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimensionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimensionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationCustomizedMetricSpecificationMetricDimension.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the dimension.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the dimension.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the dimension.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the dimension.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the dimension.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PolicyTargetTrackingConfigurationPredefinedMetricSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PolicyTargetTrackingConfigurationPredefinedMetricSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PolicyTargetTrackingConfigurationPredefinedMetricSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationPredefinedMetricSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#PolicyTargetTrackingConfigurationPredefinedMetricSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationPredefinedMetricSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.PolicyTargetTrackingConfigurationPredefinedMetricSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Predefined<wbr>Metric<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The metric type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifies the resource associated with the metric type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Predefined<wbr>Metric<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The metric type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifies the resource associated with the metric type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">predefined<wbr>Metric<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The metric type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifies the resource associated with the metric type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">predefined<wbr>Metric<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The metric type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifies the resource associated with the metric type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








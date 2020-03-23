
---
title: "Schedule"
block_external_search_index: true
---

Provides an AutoScaling Schedule resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foobarGroup = new aws.autoscaling.Group("foobar", {
    availabilityZones: ["us-west-2a"],
    forceDelete: true,
    healthCheckGracePeriod: 300,
    healthCheckType: "ELB",
    maxSize: 1,
    minSize: 1,
    terminationPolicies: ["OldestInstance"],
});
const foobarSchedule = new aws.autoscaling.Schedule("foobar", {
    autoscalingGroupName: foobarGroup.name,
    desiredCapacity: 0,
    endTime: "2016-12-12T06:00:00Z",
    maxSize: 1,
    minSize: 0,
    scheduledActionName: "foobar",
    startTime: "2016-12-11T18:00:00Z",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/autoscaling_schedule.html.markdown.



## Create a Schedule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#Schedule">Schedule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#ScheduleArgs">ScheduleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Schedule</span><span class="p">(resource_name, opts=None, </span>autoscaling_group_name=None<span class="p">, </span>desired_capacity=None<span class="p">, </span>end_time=None<span class="p">, </span>max_size=None<span class="p">, </span>min_size=None<span class="p">, </span>recurrence=None<span class="p">, </span>scheduled_action_name=None<span class="p">, </span>start_time=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSchedule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#ScheduleArgs">ScheduleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#Schedule">Schedule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.Schedule.html">Schedule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.ScheduleArgs.html">ScheduleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">End<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recurrence<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">End<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recurrence<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">end<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recurrence<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">autoscaling_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">end_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recurrence<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scheduled_<wbr>action_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Schedule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">End<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Recurrence<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">End<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Recurrence<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">end<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">recurrence<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-"
            title="">start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">desired_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">end_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">min_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">recurrence<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scheduled_<wbr>action_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-"
            title="">start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Schedule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#ScheduleState">ScheduleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/autoscaling/#Schedule">Schedule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>autoscaling_group_name=None<span class="p">, </span>desired_capacity=None<span class="p">, </span>end_time=None<span class="p">, </span>max_size=None<span class="p">, </span>min_size=None<span class="p">, </span>recurrence=None<span class="p">, </span>scheduled_action_name=None<span class="p">, </span>start_time=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSchedule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#ScheduleState">ScheduleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/autoscaling?tab=doc#Schedule">Schedule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.Schedule.html">Schedule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Autoscaling.ScheduleState.html">ScheduleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Schedule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">End<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recurrence<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">End<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recurrence<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">end<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recurrence<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheduled<wbr>Action<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN assigned by AWS to the autoscaling schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or Amazon Resource Name (ARN) of the Auto Scaling group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of EC2 instances that should be running in the group. Default 0.  Set to -1 if you don&#39;t want to change the desired capacity at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">end_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time for this action to end, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the maximum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum size for the Auto Scaling group. Default 0.
Set to -1 if you don&#39;t want to change the minimum size at the scheduled time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recurrence<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time when recurring future actions will start. Start time is specified by the user following the Unix cron syntax format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheduled_<wbr>action_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of this scaling action.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time for this action to start, in &#34;YYYY-MM-DDThh:mm:ssZ&#34; format in UTC/GMT only (for example, 2014-06-01T00:00:00Z ).
If you try to schedule your action in the past, Auto Scaling returns an error message.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







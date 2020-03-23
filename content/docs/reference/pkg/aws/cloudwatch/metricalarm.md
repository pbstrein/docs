
---
title: "MetricAlarm"
block_external_search_index: true
---

Provides a CloudWatch Metric Alarm resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foobar = new aws.cloudwatch.MetricAlarm("foobar", {
    alarmDescription: "This metric monitors ec2 cpu utilization",
    comparisonOperator: "GreaterThanOrEqualToThreshold",
    evaluationPeriods: 2,
    insufficientDataActions: [],
    metricName: "CPUUtilization",
    namespace: "AWS/EC2",
    period: 120,
    statistic: "Average",
    threshold: 80,
});
```

## Example in Conjunction with Scaling Policies

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const batPolicy = new aws.autoscaling.Policy("bat", {
    adjustmentType: "ChangeInCapacity",
    autoscalingGroupName: aws_autoscaling_group_bar.name,
    cooldown: 300,
    scalingAdjustment: 4,
});
const batMetricAlarm = new aws.cloudwatch.MetricAlarm("bat", {
    alarmActions: [batPolicy.arn],
    alarmDescription: "This metric monitors ec2 cpu utilization",
    comparisonOperator: "GreaterThanOrEqualToThreshold",
    dimensions: {
        AutoScalingGroupName: aws_autoscaling_group_bar.name,
    },
    evaluationPeriods: 2,
    metricName: "CPUUtilization",
    namespace: "AWS/EC2",
    period: 120,
    statistic: "Average",
    threshold: 80,
});
```

## Example with an Expression

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foobar = new aws.cloudwatch.MetricAlarm("foobar", {
    alarmDescription: "Request error rate has exceeded 10%",
    comparisonOperator: "GreaterThanOrEqualToThreshold",
    evaluationPeriods: 2,
    insufficientDataActions: [],
    metricQueries: [
        {
            expression: "m2/m1*100",
            id: "e1",
            label: "Error Rate",
            returnData: true,
        },
        {
            id: "m1",
            metric: {
                dimensions: {
                    LoadBalancer: "app/web",
                },
                metricName: "RequestCount",
                namespace: "AWS/ApplicationELB",
                period: 120,
                stat: "Sum",
                unit: "Count",
            },
        },
        {
            id: "m2",
            metric: {
                dimensions: {
                    LoadBalancer: "app/web",
                },
                metricName: "HTTPCode_ELB_5XX_Count",
                namespace: "AWS/ApplicationELB",
                period: 120,
                stat: "Sum",
                unit: "Count",
            },
        },
    ],
    threshold: 10,
});
```

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const xxAnomalyDetection = new aws.cloudwatch.MetricAlarm("xx_anomaly_detection", {
    alarmDescription: "This metric monitors ec2 cpu utilization",
    comparisonOperator: "GreaterThanUpperThreshold",
    evaluationPeriods: 2,
    insufficientDataActions: [],
    metricQueries: [
        {
            expression: "ANOMALY_DETECTION_BAND(m1)",
            id: "e1",
            label: "CPUUtilization (Expected)",
            returnData: true,
        },
        {
            id: "m1",
            metric: {
                dimensions: {
                    InstanceId: "i-abc123",
                },
                metricName: "CPUUtilization",
                namespace: "AWS/EC2",
                period: 120,
                stat: "Average",
                unit: "Count",
            },
            returnData: true,
        },
    ],
    thresholdMetricId: "e1",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cloudwatch_metric_alarm.html.markdown.



## Create a MetricAlarm Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudwatch/#MetricAlarm">MetricAlarm</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudwatch/#MetricAlarmArgs">MetricAlarmArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">MetricAlarm</span><span class="p">(resource_name, opts=None, </span>actions_enabled=None<span class="p">, </span>alarm_actions=None<span class="p">, </span>alarm_description=None<span class="p">, </span>comparison_operator=None<span class="p">, </span>datapoints_to_alarm=None<span class="p">, </span>dimensions=None<span class="p">, </span>evaluate_low_sample_count_percentiles=None<span class="p">, </span>evaluation_periods=None<span class="p">, </span>extended_statistic=None<span class="p">, </span>insufficient_data_actions=None<span class="p">, </span>metric_name=None<span class="p">, </span>metric_queries=None<span class="p">, </span>name=None<span class="p">, </span>namespace=None<span class="p">, </span>ok_actions=None<span class="p">, </span>period=None<span class="p">, </span>statistic=None<span class="p">, </span>tags=None<span class="p">, </span>threshold=None<span class="p">, </span>threshold_metric_id=None<span class="p">, </span>treat_missing_data=None<span class="p">, </span>unit=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewMetricAlarm<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarmArgs">MetricAlarmArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarm">MetricAlarm</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarm.html">MetricAlarm</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarmArgs.html">MetricAlarmArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dimensions<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">List&lt;Metric<wbr>Alarm<wbr>Metric<wbr>Query<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]interface{}</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dimensions<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]interface{}</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">[]Metric<wbr>Alarm<wbr>Metric<wbr>Query</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]interface{}</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statistic<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string | Topic[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dimensions<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string | Topic[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">Metric<wbr>Alarm<wbr>Metric<wbr>Query[]?</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string | Topic[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">actions_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[Topic>]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">comparison_<wbr>operator<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">datapoints_<wbr>to_<wbr>alarm<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dimensions<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">evaluate_<wbr>low_<wbr>sample_<wbr>count_<wbr>percentiles<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">evaluation_<wbr>periods<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">extended_<wbr>statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insufficient_<wbr>data_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[Topic>]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">List[Metric<wbr>Alarm<wbr>Metric<wbr>Query]</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ok_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[Topic>]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold_<wbr>metric_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">treat_<wbr>missing_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## MetricAlarm Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dimensions<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">List&lt;Metric<wbr>Alarm<wbr>Metric<wbr>Query&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Threshold<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dimensions<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">[]Metric<wbr>Alarm<wbr>Metric<wbr>Query</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Namespace<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Statistic<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Threshold<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dimensions<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-"
            title="">extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">Metric<wbr>Alarm<wbr>Metric<wbr>Query[]?</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-"
            title="">namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-"
            title="">statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">threshold<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">actions_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">alarm_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">alarm_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">comparison_<wbr>operator<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">datapoints_<wbr>to_<wbr>alarm<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dimensions<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">evaluate_<wbr>low_<wbr>sample_<wbr>count_<wbr>percentiles<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">evaluation_<wbr>periods<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-"
            title="">extended_<wbr>statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-"
            title="">insufficient_<wbr>data_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric_<wbr>queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">List[Metric<wbr>Alarm<wbr>Metric<wbr>Query]</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-"
            title="">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ok_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-"
            title="">period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-"
            title="">statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-"
            title="">threshold_<wbr>metric_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">treat_<wbr>missing_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing MetricAlarm Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudwatch/#MetricAlarmState">MetricAlarmState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudwatch/#MetricAlarm">MetricAlarm</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>actions_enabled=None<span class="p">, </span>alarm_actions=None<span class="p">, </span>alarm_description=None<span class="p">, </span>arn=None<span class="p">, </span>comparison_operator=None<span class="p">, </span>datapoints_to_alarm=None<span class="p">, </span>dimensions=None<span class="p">, </span>evaluate_low_sample_count_percentiles=None<span class="p">, </span>evaluation_periods=None<span class="p">, </span>extended_statistic=None<span class="p">, </span>insufficient_data_actions=None<span class="p">, </span>metric_name=None<span class="p">, </span>metric_queries=None<span class="p">, </span>name=None<span class="p">, </span>namespace=None<span class="p">, </span>ok_actions=None<span class="p">, </span>period=None<span class="p">, </span>statistic=None<span class="p">, </span>tags=None<span class="p">, </span>threshold=None<span class="p">, </span>threshold_metric_id=None<span class="p">, </span>treat_missing_data=None<span class="p">, </span>unit=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetMetricAlarm<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarmState">MetricAlarmState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarm">MetricAlarm</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarm.html">MetricAlarm</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarmState.html">MetricAlarmState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing MetricAlarm resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dimensions<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">List&lt;Metric<wbr>Alarm<wbr>Metric<wbr>Query<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]interface{}</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dimensions<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]interface{}</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">[]Metric<wbr>Alarm<wbr>Metric<wbr>Query</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]interface{}</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statistic<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">actions<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string | Topic[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">comparison<wbr>Operator<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">datapoints<wbr>To<wbr>Alarm<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dimensions<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">evaluate<wbr>Low<wbr>Sample<wbr>Count<wbr>Percentiles<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">evaluation<wbr>Periods<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">extended<wbr>Statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insufficient<wbr>Data<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string | Topic[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">Metric<wbr>Alarm<wbr>Metric<wbr>Query[]?</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ok<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string | Topic[]?</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statistic<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<wbr>Metric<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">treat<wbr>Missing<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">actions_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether or not actions should be executed during any changes to the alarm&#39;s state. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[Topic>]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an ALARM state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alarm_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description for the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the cloudwatch metric alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">comparison_<wbr>operator<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The arithmetic operation to use when comparing the specified Statistic and Threshold. The specified Statistic value is used as the first operand. Either of the following is supported: `GreaterThanOrEqualToThreshold`, `GreaterThanThreshold`, `LessThanThreshold`, `LessThanOrEqualToThreshold`. Additionally, the values  `LessThanLowerOrGreaterThanUpperThreshold`, `LessThanLowerThreshold`, and `GreaterThanUpperThreshold` are used only for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">datapoints_<wbr>to_<wbr>alarm<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of datapoints that must be breaching to trigger the alarm.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dimensions<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">evaluate_<wbr>low_<wbr>sample_<wbr>count_<wbr>percentiles<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used only for alarms
based on percentiles. If you specify `ignore`, the alarm state will not
change during periods with too few data points to be statistically significant.
If you specify `evaluate` or omit this parameter, the alarm will always be
evaluated and possibly change state no matter how many data points are available.
The following values are supported: `ignore`, and `evaluate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">evaluation_<wbr>periods<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of periods over which data is compared to the specified threshold.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">extended_<wbr>statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The percentile statistic for the metric associated with the alarm. Specify a value between p0.0 and p100.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">insufficient_<wbr>data_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[Topic>]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an INSUFFICIENT_DATA state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>queries<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquery">List[Metric<wbr>Alarm<wbr>Metric<wbr>Query]</a></span>
    </dt>
    <dd>{{% md %}}Enables you to create an alarm based on a metric math expression. You may specify at most 20.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the alarm. This name must be unique within the user&#39;s AWS account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ok_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type">List[Topic>]</span>
    </dt>
    <dd>{{% md %}}The list of actions to execute when this alarm transitions into an OK state from any other state. Each action is specified as an Amazon Resource Name (ARN).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statistic<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to the alarm&#39;s associated metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The value against which the specified statistic is compared. This parameter is required for alarms based on static thresholds, but should not be used for alarms based on anomaly detection models.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold_<wbr>metric_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If this is an alarm based on an anomaly detection model, make this value match the ID of the ANOMALY_DETECTION_BAND function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">treat_<wbr>missing_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Sets how this alarm is to handle missing data points. The following values are supported: `missing`, `ignore`, `breaching` and `notBreaching`. Defaults to `missing`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### MetricAlarmMetricQuery
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MetricAlarmMetricQuery">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MetricAlarmMetricQuery">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarmMetricQueryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarmMetricQueryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarmMetricQueryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarmMetricQuery.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The math expression to be performed on the returned data, if this object is performing a math expression. This expression can use the id of the other metrics to refer to those metrics, and can also use the id of other expressions to use the result of those expressions. For more information about metric math expressions, see Metric Math Syntax and Functions in the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-metric-math.html#metric-math-syntax).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short name used to tie this object to the results in the response. If you are performing math expressions on this set of data, this name represents that data and can serve as a variable in the mathematical expression. The valid characters are letters, numbers, and underscore. The first character must be a lowercase letter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Label<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable label for this metric or expression. This is especially useful if this is an expression, so that you know what the value represents.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquerymetric">Metric<wbr>Alarm<wbr>Metric<wbr>Query<wbr>Metric<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The metric to be returned, along with statistics, period, and units. Use this parameter only if this object is retrieving a metric and not performing a math expression on returned data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Return<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specify exactly one `metric_query` to be `true` to use that `metric_query` result as the alarm.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Expression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The math expression to be performed on the returned data, if this object is performing a math expression. This expression can use the id of the other metrics to refer to those metrics, and can also use the id of other expressions to use the result of those expressions. For more information about metric math expressions, see Metric Math Syntax and Functions in the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-metric-math.html#metric-math-syntax).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short name used to tie this object to the results in the response. If you are performing math expressions on this set of data, this name represents that data and can serve as a variable in the mathematical expression. The valid characters are letters, numbers, and underscore. The first character must be a lowercase letter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Label<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A human-readable label for this metric or expression. This is especially useful if this is an expression, so that you know what the value represents.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquerymetric">*Metric<wbr>Alarm<wbr>Metric<wbr>Query<wbr>Metric</a></span>
    </dt>
    <dd>{{% md %}}The metric to be returned, along with statistics, period, and units. Use this parameter only if this object is retrieving a metric and not performing a math expression on returned data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Return<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specify exactly one `metric_query` to be `true` to use that `metric_query` result as the alarm.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The math expression to be performed on the returned data, if this object is performing a math expression. This expression can use the id of the other metrics to refer to those metrics, and can also use the id of other expressions to use the result of those expressions. For more information about metric math expressions, see Metric Math Syntax and Functions in the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-metric-math.html#metric-math-syntax).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short name used to tie this object to the results in the response. If you are performing math expressions on this set of data, this name represents that data and can serve as a variable in the mathematical expression. The valid characters are letters, numbers, and underscore. The first character must be a lowercase letter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">label<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A human-readable label for this metric or expression. This is especially useful if this is an expression, so that you know what the value represents.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquerymetric">Metric<wbr>Alarm<wbr>Metric<wbr>Query<wbr>Metric?</a></span>
    </dt>
    <dd>{{% md %}}The metric to be returned, along with statistics, period, and units. Use this parameter only if this object is retrieving a metric and not performing a math expression on returned data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">return<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specify exactly one `metric_query` to be `true` to use that `metric_query` result as the alarm.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">expression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The math expression to be performed on the returned data, if this object is performing a math expression. This expression can use the id of the other metrics to refer to those metrics, and can also use the id of other expressions to use the result of those expressions. For more information about metric math expressions, see Metric Math Syntax and Functions in the [Amazon CloudWatch User Guide](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/using-metric-math.html#metric-math-syntax).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short name used to tie this object to the results in the response. If you are performing math expressions on this set of data, this name represents that data and can serve as a variable in the mathematical expression. The valid characters are letters, numbers, and underscore. The first character must be a lowercase letter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">label<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A human-readable label for this metric or expression. This is especially useful if this is an expression, so that you know what the value represents.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<span class="property-indicator"></span>
        <span class="property-type"><a href="#metricalarmmetricquerymetric">Dict[Metric<wbr>Alarm<wbr>Metric<wbr>Query<wbr>Metric]</a></span>
    </dt>
    <dd>{{% md %}}The metric to be returned, along with statistics, period, and units. Use this parameter only if this object is retrieving a metric and not performing a math expression on returned data.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">return<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specify exactly one `metric_query` to be `true` to use that `metric_query` result as the alarm.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MetricAlarmMetricQueryMetric
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MetricAlarmMetricQueryMetric">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MetricAlarmMetricQueryMetric">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarmMetricQueryMetricArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudwatch?tab=doc#MetricAlarmMetricQueryMetricOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarmMetricQueryMetricArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudwatch.MetricAlarmMetricQueryMetric.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Dimensions<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Period<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stat<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to this metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Dimensions<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Namespace<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Period<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stat<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to this metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">dimensions<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">period<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stat<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to this metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">dimensions<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The dimensions for this metric.  For the list of available dimensions see the AWS documentation [here](http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for this metric.
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">namespace<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace for this metric. See docs for the [list of namespaces](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/aws-namespaces.html).
See docs for [supported metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The period in seconds over which the specified `stat` is applied.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stat<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The statistic to apply to this metric.
Either of the following is supported: `SampleCount`, `Average`, `Sum`, `Minimum`, `Maximum`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unit for this metric.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








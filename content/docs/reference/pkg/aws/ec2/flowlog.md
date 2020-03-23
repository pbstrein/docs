
---
title: "FlowLog"
block_external_search_index: true
---

Provides a VPC/Subnet/ENI Flow Log to capture IP traffic for a specific network
interface, subnet, or VPC. Logs are sent to a CloudWatch Log Group or a S3 Bucket.

## Example Usage

### CloudWatch Logging

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleLogGroup = new aws.cloudwatch.LogGroup("example", {});
const exampleRole = new aws.iam.Role("example", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "",
      "Effect": "Allow",
      "Principal": {
        "Service": "vpc-flow-logs.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
`,
});
const exampleFlowLog = new aws.ec2.FlowLog("example", {
    iamRoleArn: exampleRole.arn,
    logDestination: exampleLogGroup.arn,
    trafficType: "ALL",
    vpcId: aws_vpc_example.id,
});
const exampleRolePolicy = new aws.iam.RolePolicy("example", {
    policy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": [
        "logs:CreateLogGroup",
        "logs:CreateLogStream",
        "logs:PutLogEvents",
        "logs:DescribeLogGroups",
        "logs:DescribeLogStreams"
      ],
      "Effect": "Allow",
      "Resource": "*"
    }
  ]
}
`,
    role: exampleRole.id,
});
```

### S3 Logging

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleBucket = new aws.s3.Bucket("example", {});
const exampleFlowLog = new aws.ec2.FlowLog("example", {
    logDestination: exampleBucket.arn,
    logDestinationType: "s3",
    trafficType: "ALL",
    vpcId: aws_vpc_example.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/flow_log.html.markdown.



## Create a FlowLog Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#FlowLog">FlowLog</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#FlowLogArgs">FlowLogArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">FlowLog</span><span class="p">(resource_name, opts=None, </span>eni_id=None<span class="p">, </span>iam_role_arn=None<span class="p">, </span>log_destination=None<span class="p">, </span>log_destination_type=None<span class="p">, </span>log_format=None<span class="p">, </span>log_group_name=None<span class="p">, </span>subnet_id=None<span class="p">, </span>traffic_type=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFlowLog<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#FlowLogArgs">FlowLogArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#FlowLog">FlowLog</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.FlowLog.html">FlowLog</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.FlowLogArgs.html">FlowLogArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">eni_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>destination_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">traffic_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## FlowLog Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-"
            title="">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">eni_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>destination_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-"
            title="">log_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-"
            title="">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing FlowLog Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#FlowLogState">FlowLogState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#FlowLog">FlowLog</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>eni_id=None<span class="p">, </span>iam_role_arn=None<span class="p">, </span>log_destination=None<span class="p">, </span>log_destination_type=None<span class="p">, </span>log_format=None<span class="p">, </span>log_group_name=None<span class="p">, </span>subnet_id=None<span class="p">, </span>traffic_type=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFlowLog<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#FlowLogState">FlowLogState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#FlowLog">FlowLog</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.FlowLog.html">FlowLog</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.FlowLogState.html">FlowLogState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing FlowLog resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">eni<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Destination<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">eni_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Elastic Network Interface ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the IAM role that&#39;s used to post flow logs to a CloudWatch Logs log group
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the logging destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>destination_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the logging destination. Valid values: `cloud-watch-logs`, `s3`. Default: `cloud-watch-logs`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fields to include in the flow log record, in the order in which they should appear.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">log_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `log_destination` instead. The name of the CloudWatch log group.
{{% /md %}}<span class="property-deprecated">use &#39;log_destination&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of traffic to capture. Valid values: `ACCEPT`,`REJECT`, `ALL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}VPC ID to attach to
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








---
title: "Job"
block_external_search_index: true
---

Provides a Glue Job resource.

> Glue functionality, such as monitoring and logging of jobs, is typically managed with the `default_arguments` argument. See the [Special Parameters Used by AWS Glue](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-etl-glue-arguments.html) topic in the Glue developer guide for additional information.

## Example Usage

### Python Job

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Job("example", {
    command: {
        scriptLocation: pulumi.interpolate`s3://${aws_s3_bucket_example.bucket}/example.py`,
    },
    roleArn: aws_iam_role_example.arn,
});
```

### Scala Job

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Job("example", {
    command: {
        scriptLocation: pulumi.interpolate`s3://${aws_s3_bucket_example.bucket}/example.scala`,
    },
    defaultArguments: {
        "--job-language": "scala",
    },
    roleArn: aws_iam_role_example.arn,
});
```

### Enabling CloudWatch Logs and Metrics

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleLogGroup = new aws.cloudwatch.LogGroup("example", {
    retentionInDays: 14,
});
const exampleJob = new aws.glue.Job("example", {
    defaultArguments: {
        // ... potentially other arguments ...
        "--continuous-log-logGroup": exampleLogGroup.name,
        "--enable-continuous-cloudwatch-log": "true",
        "--enable-continuous-log-filter": "true",
        "--enable-metrics": "",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glue_job.html.markdown.



## Create a Job Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Job">Job</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#JobArgs">JobArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Job</span><span class="p">(resource_name, opts=None, </span>allocated_capacity=None<span class="p">, </span>command=None<span class="p">, </span>connections=None<span class="p">, </span>default_arguments=None<span class="p">, </span>description=None<span class="p">, </span>execution_property=None<span class="p">, </span>glue_version=None<span class="p">, </span>max_capacity=None<span class="p">, </span>max_retries=None<span class="p">, </span>name=None<span class="p">, </span>notification_property=None<span class="p">, </span>number_of_workers=None<span class="p">, </span>role_arn=None<span class="p">, </span>security_configuration=None<span class="p">, </span>tags=None<span class="p">, </span>timeout=None<span class="p">, </span>worker_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewJob<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobArgs">JobArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Job">Job</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Job.html">Job</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobArgs.html">JobArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-required"
            title="Required">Command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connections<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-required"
            title="Required">Command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connections<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">*Job<wbr>Execution<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">*Job<wbr>Notification<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-required"
            title="Required">command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connections<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property?</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property?</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocated_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-required"
            title="Required">command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Dict[Job<wbr>Command]</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connections<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>arguments<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution_<wbr>property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Dict[Job<wbr>Execution<wbr>Property]</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">glue_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>retries<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Dict[Job<wbr>Notification<wbr>Property]</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>of_<wbr>workers<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">worker_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Job Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-"
            title="">Command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connections<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">double</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-"
            title="">Command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connections<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">float64</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-"
            title="">command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connections<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-"
            title="">notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-"
            title="">worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allocated_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-"
            title="">command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Dict[Job<wbr>Command]</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connections<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>arguments<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution_<wbr>property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Dict[Job<wbr>Execution<wbr>Property]</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">glue_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>retries<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-"
            title="">notification_<wbr>property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Dict[Job<wbr>Notification<wbr>Property]</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number_<wbr>of_<wbr>workers<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-"
            title="">worker_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Job Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#JobState">JobState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Job">Job</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allocated_capacity=None<span class="p">, </span>arn=None<span class="p">, </span>command=None<span class="p">, </span>connections=None<span class="p">, </span>default_arguments=None<span class="p">, </span>description=None<span class="p">, </span>execution_property=None<span class="p">, </span>glue_version=None<span class="p">, </span>max_capacity=None<span class="p">, </span>max_retries=None<span class="p">, </span>name=None<span class="p">, </span>notification_property=None<span class="p">, </span>number_of_workers=None<span class="p">, </span>role_arn=None<span class="p">, </span>security_configuration=None<span class="p">, </span>tags=None<span class="p">, </span>timeout=None<span class="p">, </span>worker_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetJob<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobState">JobState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Job">Job</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Job.html">Job</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobState.html">JobState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Job resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connections<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">*Job<wbr>Command</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connections<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">*Job<wbr>Execution<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">*Job<wbr>Notification<wbr>Property</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocated<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Job<wbr>Command?</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connections<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Arguments<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Job<wbr>Execution<wbr>Property?</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">glue<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Retries<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Job<wbr>Notification<wbr>Property?</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Workers<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">worker<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocated_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** (Optional) The number of AWS Glue data processing units (DPUs) to allocate to this Job. At least 2 DPUs need to be allocated; the default is 10. A DPU is a relative measure of processing power that consists of 4 vCPUs of compute capacity and 16 GB of memory.
{{% /md %}}<span class="property-deprecated">Please use attribute `max_capacity&#39; instead. This attribute might be removed in future releases.</span></dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Glue Job
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">command<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobcommand">Dict[Job<wbr>Command]</a></span>
    </dt>
    <dd>{{% md %}}The command of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connections<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of connections used for this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>arguments<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The map of default arguments for this job. You can specify arguments here that your own job-execution script consumes, as well as arguments that AWS Glue itself consumes. For information about how to specify and consume your own Job arguments, see the [Calling AWS Glue APIs in Python](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-calling.html) topic in the developer guide. For information about the key-value pairs that AWS Glue consumes to set up your job, see the [Special Parameters Used by AWS Glue](http://docs.aws.amazon.com/glue/latest/dg/aws-glue-programming-python-glue-arguments.html) topic in the developer guide.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution_<wbr>property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobexecutionproperty">Dict[Job<wbr>Execution<wbr>Property]</a></span>
    </dt>
    <dd>{{% md %}}Execution property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">glue_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of glue to use, for example &#34;1.0&#34;. For information about available versions, see the [AWS Glue Release Notes](https://docs.aws.amazon.com/glue/latest/dg/release-notes.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of AWS Glue data processing units (DPUs) that can be allocated when this job runs. `Required` when `pythonshell` is set, accept either `0.0625` or `1.0`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>retries<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of times to retry this job if it fails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>property<span class="property-indicator"></span>
        <span class="property-type"><a href="#jobnotificationproperty">Dict[Job<wbr>Notification<wbr>Property]</a></span>
    </dt>
    <dd>{{% md %}}Notification property of the job. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>of_<wbr>workers<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of workers of a defined workerType that are allocated when a job runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the IAM role associated with this job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Security Configuration to be associated with the job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The job timeout in minutes. The default is 2880 minutes (48 hours).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">worker_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of predefined worker that is allocated when a job runs. Accepts a value of Standard, G.1X, or G.2X.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### JobCommand
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#JobCommand">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#JobCommand">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobCommandArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobCommandOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobCommandArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobCommand.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Python<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Python version being used to execute a Python shell job. Allowed values are 2 or 3.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Script<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 path to a script that executes a job.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Python<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Python version being used to execute a Python shell job. Allowed values are 2 or 3.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Script<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 path to a script that executes a job.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">python<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Python version being used to execute a Python shell job. Allowed values are 2 or 3.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">script<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 path to a script that executes a job.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the job command. Defaults to `glueetl`. Use `pythonshell` for Python Shell Job Type, `max_capacity` needs to be set if `pythonshell` is chosen.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">python<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Python version being used to execute a Python shell job. Allowed values are 2 or 3.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">script<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the S3 path to a script that executes a job.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### JobExecutionProperty
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#JobExecutionProperty">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#JobExecutionProperty">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobExecutionPropertyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobExecutionPropertyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobExecutionPropertyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobExecutionProperty.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrent<wbr>Runs<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum number of concurrent runs allowed for a job. The default is 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrent<wbr>Runs<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum number of concurrent runs allowed for a job. The default is 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">max<wbr>Concurrent<wbr>Runs<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of concurrent runs allowed for a job. The default is 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">max<wbr>Concurrent<wbr>Runs<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of concurrent runs allowed for a job. The default is 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### JobNotificationProperty
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#JobNotificationProperty">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#JobNotificationProperty">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobNotificationPropertyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#JobNotificationPropertyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobNotificationPropertyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.JobNotificationProperty.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Notify<wbr>Delay<wbr>After<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}After a job run starts, the number of minutes to wait before sending a job run delay notification.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Notify<wbr>Delay<wbr>After<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}After a job run starts, the number of minutes to wait before sending a job run delay notification.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">notify<wbr>Delay<wbr>After<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}After a job run starts, the number of minutes to wait before sending a job run delay notification.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">notify<wbr>Delay<wbr>After<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}After a job run starts, the number of minutes to wait before sending a job run delay notification.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








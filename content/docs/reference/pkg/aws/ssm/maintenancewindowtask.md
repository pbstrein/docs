
---
title: "MaintenanceWindowTask"
block_external_search_index: true
---

Provides an SSM Maintenance Window Task resource

## Example Usage

### Automation Tasks

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ssm.MaintenanceWindowTask("example", {
    maxConcurrency: "2",
    maxErrors: "1",
    priority: 1,
    serviceRoleArn: aws_iam_role_example.arn,
    targets: [{
        key: "InstanceIds",
        values: [aws_instance_example.id],
    }],
    taskArn: "AWS-RestartEC2Instance",
    taskInvocationParameters: {
        automationParameters: {
            documentVersion: "$LATEST",
            parameters: [{
                name: "InstanceId",
                values: [aws_instance_example.id],
            }],
        },
    },
    taskType: "AUTOMATION",
    windowId: aws_ssm_maintenance_window_example.id,
});
```

### Lambda Tasks

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ssm.MaintenanceWindowTask("example", {
    maxConcurrency: "2",
    maxErrors: "1",
    priority: 1,
    serviceRoleArn: aws_iam_role_example.arn,
    targets: [{
        key: "InstanceIds",
        values: [aws_instance_example.id],
    }],
    taskArn: aws_lambda_function_example.arn,
    taskInvocationParameters: {
        lambdaParameters: {
            clientContext: Buffer.from("{\"key1\":\"value1\"}").toString("base64"),
            payload: "{\"key1\":\"value1\"}",
        },
    },
    taskType: "LAMBDA",
    windowId: aws_ssm_maintenance_window_example.id,
});
```

### Run Command Tasks

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ssm.MaintenanceWindowTask("example", {
    maxConcurrency: "2",
    maxErrors: "1",
    priority: 1,
    serviceRoleArn: aws_iam_role_example.arn,
    targets: [{
        key: "InstanceIds",
        values: [aws_instance_example.id],
    }],
    taskArn: "AWS-RunShellScript",
    taskInvocationParameters: {
        runCommandParameters: {
            notificationConfig: {
                notificationArn: aws_sns_topic_example.arn,
                notificationEvents: ["All"],
                notificationType: ["Command"],
            },
            outputS3Bucket: aws_s3_bucket_example.bucket,
            outputS3KeyPrefix: "output",
            parameters: [{
                name: "commands",
                values: ["date"],
            }],
            serviceRoleArn: aws_iam_role_example.arn,
            timeoutSeconds: 600,
        },
    },
    taskType: "RUN_COMMAND",
    windowId: aws_ssm_maintenance_window_example.id,
});
```

### Step Function Tasks

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ssm.MaintenanceWindowTask("example", {
    maxConcurrency: "2",
    maxErrors: "1",
    priority: 1,
    serviceRoleArn: aws_iam_role_example.arn,
    targets: [{
        key: "InstanceIds",
        values: [aws_instance_example.id],
    }],
    taskArn: aws_sfn_activity_example.id,
    taskInvocationParameters: {
        stepFunctionsParameters: {
            input: "{\"key1\":\"value1\"}",
            name: "example",
        },
    },
    taskType: "STEP_FUNCTIONS",
    windowId: aws_ssm_maintenance_window_example.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ssm_maintenance_window_task.html.markdown.



## Create a MaintenanceWindowTask Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTask">MaintenanceWindowTask</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTaskArgs">MaintenanceWindowTaskArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">MaintenanceWindowTask</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>logging_info=None<span class="p">, </span>max_concurrency=None<span class="p">, </span>max_errors=None<span class="p">, </span>name=None<span class="p">, </span>priority=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>targets=None<span class="p">, </span>task_arn=None<span class="p">, </span>task_invocation_parameters=None<span class="p">, </span>task_parameters=None<span class="p">, </span>task_type=None<span class="p">, </span>window_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewMaintenanceWindowTask<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskArgs">MaintenanceWindowTaskArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTask">MaintenanceWindowTask</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTask.html">MaintenanceWindowTask</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskArgs.html">MaintenanceWindowTaskArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Target<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">Task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">*Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">[]Maintenance<wbr>Window<wbr>Task<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">[]Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">Task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">Maintenance<wbr>Window<wbr>Task<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter[]?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">max_<wbr>concurrency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max_<wbr>errors<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">List[Maintenance<wbr>Window<wbr>Task<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">task_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>invocation_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">List[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-required"
            title="Required">task_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">window_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## MaintenanceWindowTask Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Priority<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Target&gt;</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">Task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">*Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Priority<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">[]Maintenance<wbr>Window<wbr>Task<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">[]Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">Task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">priority<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">Maintenance<wbr>Window<wbr>Task<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter[]?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">max_<wbr>concurrency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>errors<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">List[Maintenance<wbr>Window<wbr>Task<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">task_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">task_<wbr>invocation_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">task_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">List[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-"
            title="">task_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">window_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing MaintenanceWindowTask Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTaskState">MaintenanceWindowTaskState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTask">MaintenanceWindowTask</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>logging_info=None<span class="p">, </span>max_concurrency=None<span class="p">, </span>max_errors=None<span class="p">, </span>name=None<span class="p">, </span>priority=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>targets=None<span class="p">, </span>task_arn=None<span class="p">, </span>task_invocation_parameters=None<span class="p">, </span>task_parameters=None<span class="p">, </span>task_type=None<span class="p">, </span>window_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetMaintenanceWindowTask<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskState">MaintenanceWindowTaskState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTask">MaintenanceWindowTask</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTask.html">MaintenanceWindowTask</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskState.html">MaintenanceWindowTaskState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing MaintenanceWindowTask resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">*Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">[]Maintenance<wbr>Window<wbr>Task<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">[]Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">Maintenance<wbr>Window<wbr>Task<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Invocation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter[]?</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasklogginginfo">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Logging<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about an Amazon S3 bucket to write instance-level logs to. Use `task_invocation_parameters` configuration block `run_command_parameters` configuration block `output_s3_*` arguments instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>concurrency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets this task can be run for in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>errors<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of errors allowed before this task stops being scheduled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority of the task in the Maintenance Window, the lower the number the higher the priority. Tasks in a Maintenance Window are scheduled in priority order with tasks that have the same priority scheduled in parallel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktarget">List[Maintenance<wbr>Window<wbr>Task<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or window target ids). Instances are specified using Key=InstanceIds,Values=instanceid1,instanceid2. Window target ids are specified using Key=WindowTargetIds,Values=window target id1, window target id2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the task to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>invocation_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for task execution. This argument is conflict with `task_parameters` and `logging_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskparameter">List[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}A structure containing information about parameters required by the particular `task_arn`. Use `parameter` configuration blocks under the `task_invocation_parameters` configuration block instead. Conflicts with `task_invocation_parameters`. Documented below.
{{% /md %}}<span class="property-deprecated">use &#39;task_invocation_parameters&#39; argument instead</span></dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of task being registered. The only allowed value is `RUN_COMMAND`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">window_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the task with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### MaintenanceWindowTaskLoggingInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskLoggingInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskLoggingInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskLoggingInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskLoggingInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskLoggingInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskLoggingInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Automation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for an AUTOMATION task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameterslambdaparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Lambda<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a LAMBDA task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Run<wbr>Command<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a RUN_COMMAND task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Step<wbr>Functions<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersstepfunctionsparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Step<wbr>Functions<wbr>Parameters<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a STEP_FUNCTIONS task type. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Automation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for an AUTOMATION task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameterslambdaparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Lambda<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a LAMBDA task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Run<wbr>Command<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a RUN_COMMAND task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Step<wbr>Functions<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersstepfunctionsparameters">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Step<wbr>Functions<wbr>Parameters</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a STEP_FUNCTIONS task type. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">automation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for an AUTOMATION task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameterslambdaparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Lambda<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a LAMBDA task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">run<wbr>Command<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a RUN_COMMAND task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">step<wbr>Functions<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersstepfunctionsparameters">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Step<wbr>Functions<wbr>Parameters?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a STEP_FUNCTIONS task type. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">automation<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for an AUTOMATION task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparameterslambdaparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Lambda<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a LAMBDA task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">run<wbr>Command<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a RUN_COMMAND task type. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">step<wbr>Functions<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersstepfunctionsparameters">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Step<wbr>Functions<wbr>Parameters]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for a STEP_FUNCTIONS task type. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersAutomationParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersAutomationParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersAutomationParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersAutomationParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersAutomationParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersAutomationParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersAutomationParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of an Automation document to use during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparametersparameter">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters<wbr>Parameter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of an Automation document to use during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparametersparameter">[]Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of an Automation document to use during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparametersparameter">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters<wbr>Parameter[]?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">document_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of an Automation document to use during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersautomationparametersparameter">List[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Automation<wbr>Parameters<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersAutomationParametersParameter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersLambdaParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersLambdaParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersLambdaParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersLambdaParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersLambdaParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersLambdaParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersLambdaParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Client<wbr>Context<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Pass client-specific information to the Lambda function that you are invoking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Payload<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON to provide to your Lambda function as input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify a Lambda function version or alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Client<wbr>Context<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Pass client-specific information to the Lambda function that you are invoking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Payload<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}JSON to provide to your Lambda function as input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify a Lambda function version or alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">client<wbr>Context<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Pass client-specific information to the Lambda function that you are invoking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">payload<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}JSON to provide to your Lambda function as input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify a Lambda function version or alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">client<wbr>Context<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Pass client-specific information to the Lambda function that you are invoking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">payload<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}JSON to provide to your Lambda function as input.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify a Lambda function version or alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersRunCommandParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersRunCommandParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersRunCommandParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersRunCommandParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Information about the command(s) to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SHA-256 or SHA-1 hash created by the system when the document was created. SHA-1 hashes have been deprecated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SHA-256 or SHA-1. SHA-1 hashes have been deprecated. Valid values: `Sha256` and `Sha1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersnotificationconfig">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Notification<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configurations for sending notifications about command status changes on a per-instance basis. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket subfolder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersparameter">List&lt;Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Parameter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}If this time is reached and the command has not already started executing, it doesn&#39;t run.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Information about the command(s) to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SHA-256 or SHA-1 hash created by the system when the document was created. SHA-1 hashes have been deprecated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}SHA-256 or SHA-1. SHA-1 hashes have been deprecated. Valid values: `Sha256` and `Sha1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersnotificationconfig">*Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Notification<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configurations for sending notifications about command status changes on a per-instance basis. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket subfolder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersparameter">[]Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Parameter</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}If this time is reached and the command has not already started executing, it doesn&#39;t run.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Information about the command(s) to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SHA-256 or SHA-1 hash created by the system when the document was created. SHA-1 hashes have been deprecated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}SHA-256 or SHA-1. SHA-1 hashes have been deprecated. Valid values: `Sha256` and `Sha1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersnotificationconfig">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Notification<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configurations for sending notifications about command status changes on a per-instance basis. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket subfolder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersparameter">Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Parameter[]?</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}If this time is reached and the command has not already started executing, it doesn&#39;t run.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Information about the command(s) to execute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SHA-256 or SHA-1 hash created by the system when the document was created. SHA-1 hashes have been deprecated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Hash<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SHA-256 or SHA-1. SHA-1 hashes have been deprecated. Valid values: `Sha256` and `Sha1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersnotificationconfig">Dict[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Notification<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configurations for sending notifications about command status changes on a per-instance basis. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>S3Bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Amazon S3 bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket subfolder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtasktaskinvocationparametersruncommandparametersparameter">List[Maintenance<wbr>Window<wbr>Task<wbr>Task<wbr>Invocation<wbr>Parameters<wbr>Run<wbr>Command<wbr>Parameters<wbr>Parameter]</a></span>
    </dt>
    <dd>{{% md %}}The parameters for the RUN_COMMAND task execution. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM service role to assume during task execution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}If this time is reached and the command has not already started executing, it doesn&#39;t run.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersNotificationConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Notification<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. Run Command pushes notifications about command status changes to this topic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The different events for which you can receive notifications. Valid values: `All`, `InProgress`, `Success`, `TimedOut`, `Cancelled`, and `Failed`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When specified with `Command`, receive notification when the status of a command changes. When specified with `Invocation`, for commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. Valid values: `Command` and `Invocation`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Notification<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. Run Command pushes notifications about command status changes to this topic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The different events for which you can receive notifications. Valid values: `All`, `InProgress`, `Success`, `TimedOut`, `Cancelled`, and `Failed`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When specified with `Command`, receive notification when the status of a command changes. When specified with `Invocation`, for commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. Valid values: `Command` and `Invocation`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">notification<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. Run Command pushes notifications about command status changes to this topic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The different events for which you can receive notifications. Valid values: `All`, `InProgress`, `Success`, `TimedOut`, `Cancelled`, and `Failed`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When specified with `Command`, receive notification when the status of a command changes. When specified with `Invocation`, for commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. Valid values: `Command` and `Invocation`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">notification<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) for a Simple Notification Service (SNS) topic. Run Command pushes notifications about command status changes to this topic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The different events for which you can receive notifications. Valid values: `All`, `InProgress`, `Success`, `TimedOut`, `Cancelled`, and `Failed`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When specified with `Command`, receive notification when the status of a command changes. When specified with `Invocation`, for commands sent to multiple instances, receive notification on a per-instance basis when the status of a command changes. Valid values: `Command` and `Invocation`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersRunCommandParametersParameter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParameters
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParameters">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParameters">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParametersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParametersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParametersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskInvocationParametersStepFunctionsParameters.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Input<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The inputs for the STEP_FUNCTION task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Input<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The inputs for the STEP_FUNCTION task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">input<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The inputs for the STEP_FUNCTION task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">input<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The inputs for the STEP_FUNCTION task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### MaintenanceWindowTaskTaskParameter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTaskTaskParameter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTaskTaskParameter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskParameterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTaskTaskParameterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskParameterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTaskTaskParameter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The parameter name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The array of strings.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








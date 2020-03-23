
---
title: "TaskDefinition"
block_external_search_index: true
---

Manages a revision of an ECS task definition to be used in `aws.ecs.Service`.

## Example Usage

### With AppMesh Proxy

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as fs from "fs";

const service = new aws.ecs.TaskDefinition("service", {
    containerDefinitions: fs.readFileSync("task-definitions/service.json", "utf-8"),
    family: "service",
    proxyConfiguration: {
        containerName: "applicationContainerName",
        properties: {
            AppPorts: "8080",
            EgressIgnoredIPs: "169.254.170.2,169.254.169.254",
            IgnoredUID: "1337",
            ProxyEgressPort: 15001,
            ProxyIngressPort: 15000,
        },
        type: "APPMESH",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ecs_task_definition.html.markdown.



## Create a TaskDefinition Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#TaskDefinition">TaskDefinition</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#TaskDefinitionArgs">TaskDefinitionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">TaskDefinition</span><span class="p">(resource_name, opts=None, </span>container_definitions=None<span class="p">, </span>cpu=None<span class="p">, </span>execution_role_arn=None<span class="p">, </span>family=None<span class="p">, </span>ipc_mode=None<span class="p">, </span>memory=None<span class="p">, </span>network_mode=None<span class="p">, </span>pid_mode=None<span class="p">, </span>placement_constraints=None<span class="p">, </span>proxy_configuration=None<span class="p">, </span>requires_compatibilities=None<span class="p">, </span>tags=None<span class="p">, </span>task_role_arn=None<span class="p">, </span>volumes=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTaskDefinition<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionArgs">TaskDefinitionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinition">TaskDefinition</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinition.html">TaskDefinition</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionArgs.html">TaskDefinitionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">List&lt;Task<wbr>Definition<wbr>Placement<wbr>Constraint<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Task<wbr>Definition<wbr>Proxy<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">List&lt;Task<wbr>Definition<wbr>Volume<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">[]Task<wbr>Definition<wbr>Placement<wbr>Constraint</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">*Task<wbr>Definition<wbr>Proxy<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">[]Task<wbr>Definition<wbr>Volume</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">Task<wbr>Definition<wbr>Placement<wbr>Constraint[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Task<wbr>Definition<wbr>Proxy<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">Task<wbr>Definition<wbr>Volume[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">container_<wbr>definitions<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipc_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pid_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">List[Task<wbr>Definition<wbr>Placement<wbr>Constraint]</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Dict[Task<wbr>Definition<wbr>Proxy<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requires_<wbr>compatibilities<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">List[Task<wbr>Definition<wbr>Volume]</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## TaskDefinition Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Memory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">List&lt;Task<wbr>Definition<wbr>Placement<wbr>Constraint&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Task<wbr>Definition<wbr>Proxy<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Revision<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">List&lt;Task<wbr>Definition<wbr>Volume&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Memory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">[]Task<wbr>Definition<wbr>Placement<wbr>Constraint</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">*Task<wbr>Definition<wbr>Proxy<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Revision<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">[]Task<wbr>Definition<wbr>Volume</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-"
            title="">family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">memory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">Task<wbr>Definition<wbr>Placement<wbr>Constraint[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Task<wbr>Definition<wbr>Proxy<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">revision<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-"
            title="">volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">Task<wbr>Definition<wbr>Volume[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">container_<wbr>definitions<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-"
            title="">family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipc_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">memory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">pid_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement_<wbr>constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">List[Task<wbr>Definition<wbr>Placement<wbr>Constraint]</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">proxy_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Dict[Task<wbr>Definition<wbr>Proxy<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">requires_<wbr>compatibilities<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">revision<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">task_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-"
            title="">volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">List[Task<wbr>Definition<wbr>Volume]</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing TaskDefinition Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#TaskDefinitionState">TaskDefinitionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#TaskDefinition">TaskDefinition</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>container_definitions=None<span class="p">, </span>cpu=None<span class="p">, </span>execution_role_arn=None<span class="p">, </span>family=None<span class="p">, </span>ipc_mode=None<span class="p">, </span>memory=None<span class="p">, </span>network_mode=None<span class="p">, </span>pid_mode=None<span class="p">, </span>placement_constraints=None<span class="p">, </span>proxy_configuration=None<span class="p">, </span>requires_compatibilities=None<span class="p">, </span>revision=None<span class="p">, </span>tags=None<span class="p">, </span>task_role_arn=None<span class="p">, </span>volumes=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTaskDefinition<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionState">TaskDefinitionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinition">TaskDefinition</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinition.html">TaskDefinition</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionState.html">TaskDefinitionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing TaskDefinition resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">List&lt;Task<wbr>Definition<wbr>Placement<wbr>Constraint<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Task<wbr>Definition<wbr>Proxy<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revision<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">List&lt;Task<wbr>Definition<wbr>Volume<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Family<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">[]Task<wbr>Definition<wbr>Placement<wbr>Constraint</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">*Task<wbr>Definition<wbr>Proxy<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revision<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">[]Task<wbr>Definition<wbr>Volume</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">container<wbr>Definitions<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipc<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pid<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">Task<wbr>Definition<wbr>Placement<wbr>Constraint[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Task<wbr>Definition<wbr>Proxy<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requires<wbr>Compatibilities<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revision<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">Task<wbr>Definition<wbr>Volume[]?</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Full ARN of the Task Definition (including both `family` and `revision`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">container_<wbr>definitions<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of valid [container definitions]
(http://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_ContainerDefinition.html) provided as a
single valid JSON document. Please note that you should only provide values that are part of the container
definition document. For a detailed description of what parameters are available, see the [Task Definition Parameters]
(https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) section from the
official [Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of cpu units used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the task execution role that the Amazon ECS container agent and the Docker daemon can assume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your task definition.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipc_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPC resource namespace to be used for the containers in the task The valid values are `host`, `task`, and `none`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The amount (in MiB) of memory used by the task. If the `requires_compatibilities` is `FARGATE` this field is required.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Docker networking mode to use for the containers in the task. The valid values are `none`, `bridge`, `awsvpc`, and `host`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pid_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The process namespace to use for the containers in the task. The valid values are `host` and `task`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionplacementconstraint">List[Task<wbr>Definition<wbr>Placement<wbr>Constraint]</a></span>
    </dt>
    <dd>{{% md %}}A set of placement constraints rules that are taken into consideration during task placement. Maximum number of `placement_constraints` is `10`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionproxyconfiguration">Dict[Task<wbr>Definition<wbr>Proxy<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The proxy configuration details for the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requires_<wbr>compatibilities<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A set of launch types required by the task. The valid values are `EC2` and `FARGATE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revision<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The revision of the task in a particular family.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of IAM role that allows your Amazon ECS container task to make calls to other AWS services.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volumes<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolume">List[Task<wbr>Definition<wbr>Volume]</a></span>
    </dt>
    <dd>{{% md %}}A set of volume blocks that containers in your task may use.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### TaskDefinitionPlacementConstraint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TaskDefinitionPlacementConstraint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TaskDefinitionPlacementConstraint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionPlacementConstraintArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionPlacementConstraintOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionPlacementConstraintArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionPlacementConstraint.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Cluster Query Language expression to apply to the constraint.
For more information, see [Cluster Query Language in the Amazon EC2 Container
Service Developer
Guide](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Expression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Cluster Query Language expression to apply to the constraint.
For more information, see [Cluster Query Language in the Amazon EC2 Container
Service Developer
Guide](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Cluster Query Language expression to apply to the constraint.
For more information, see [Cluster Query Language in the Amazon EC2 Container
Service Developer
Guide](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">expression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Cluster Query Language expression to apply to the constraint.
For more information, see [Cluster Query Language in the Amazon EC2 Container
Service Developer
Guide](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TaskDefinitionProxyConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TaskDefinitionProxyConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TaskDefinitionProxyConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionProxyConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionProxyConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionProxyConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionProxyConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the container that will serve as the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Properties<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}The set of network configuration parameters to provide the Container Network Interface (CNI) plugin, specified a key-value mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the container that will serve as the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Properties<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}The set of network configuration parameters to provide the Container Network Interface (CNI) plugin, specified a key-value mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the container that will serve as the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">properties<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}The set of network configuration parameters to provide the Container Network Interface (CNI) plugin, specified a key-value mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">container_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the container that will serve as the App Mesh proxy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">properties<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}The set of network configuration parameters to provide the Container Network Interface (CNI) plugin, specified a key-value mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The proxy type. The default value is `APPMESH`. The only supported value is `APPMESH`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TaskDefinitionVolume
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TaskDefinitionVolume">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TaskDefinitionVolume">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionVolumeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionVolumeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionVolumeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionVolume.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Docker<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumedockervolumeconfiguration">Task<wbr>Definition<wbr>Volume<wbr>Docker<wbr>Volume<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a docker volume
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Efs<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumeefsvolumeconfiguration">Task<wbr>Definition<wbr>Volume<wbr>Efs<wbr>Volume<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a EFS volume. Can be used only with an EC2 type task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The path on the host container instance that is presented to the container. If not set, ECS will create a nonpersistent data volume that starts empty and is deleted after the task has finished.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the volume. This name is referenced in the `sourceVolume`
parameter of container definition in the `mountPoints` section.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Docker<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumedockervolumeconfiguration">*Task<wbr>Definition<wbr>Volume<wbr>Docker<wbr>Volume<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a docker volume
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Efs<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumeefsvolumeconfiguration">*Task<wbr>Definition<wbr>Volume<wbr>Efs<wbr>Volume<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a EFS volume. Can be used only with an EC2 type task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The path on the host container instance that is presented to the container. If not set, ECS will create a nonpersistent data volume that starts empty and is deleted after the task has finished.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the volume. This name is referenced in the `sourceVolume`
parameter of container definition in the `mountPoints` section.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">docker<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumedockervolumeconfiguration">Task<wbr>Definition<wbr>Volume<wbr>Docker<wbr>Volume<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a docker volume
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">efs<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumeefsvolumeconfiguration">Task<wbr>Definition<wbr>Volume<wbr>Efs<wbr>Volume<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a EFS volume. Can be used only with an EC2 type task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The path on the host container instance that is presented to the container. If not set, ECS will create a nonpersistent data volume that starts empty and is deleted after the task has finished.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the volume. This name is referenced in the `sourceVolume`
parameter of container definition in the `mountPoints` section.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">docker<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumedockervolumeconfiguration">Dict[Task<wbr>Definition<wbr>Volume<wbr>Docker<wbr>Volume<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a docker volume
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">efs<wbr>Volume<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#taskdefinitionvolumeefsvolumeconfiguration">Dict[Task<wbr>Definition<wbr>Volume<wbr>Efs<wbr>Volume<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Used to configure a EFS volume. Can be used only with an EC2 type task.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path on the host container instance that is presented to the container. If not set, ECS will create a nonpersistent data volume that starts empty and is deleted after the task has finished.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the volume. This name is referenced in the `sourceVolume`
parameter of container definition in the `mountPoints` section.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TaskDefinitionVolumeDockerVolumeConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TaskDefinitionVolumeDockerVolumeConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TaskDefinitionVolumeDockerVolumeConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionVolumeDockerVolumeConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionVolumeDockerVolumeConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionVolumeDockerVolumeConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionVolumeDockerVolumeConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Autoprovision<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If this value is `true`, the Docker volume is created if it does not already exist. *Note*: This field is only used if the scope is `shared`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Driver<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Docker volume driver to use. The driver value must match the driver name provided by Docker because it is used for task placement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Driver<wbr>Opts<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of Docker driver specific options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Labels<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of custom metadata to add to your Docker volume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scope for the Docker volume, which determines its lifecycle, either `task` or `shared`.  Docker volumes that are scoped to a `task` are automatically provisioned when the task starts and destroyed when the task stops. Docker volumes that are `scoped` as shared persist after the task stops.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Autoprovision<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If this value is `true`, the Docker volume is created if it does not already exist. *Note*: This field is only used if the scope is `shared`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Driver<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Docker volume driver to use. The driver value must match the driver name provided by Docker because it is used for task placement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Driver<wbr>Opts<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of Docker driver specific options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Labels<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of custom metadata to add to your Docker volume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The scope for the Docker volume, which determines its lifecycle, either `task` or `shared`.  Docker volumes that are scoped to a `task` are automatically provisioned when the task starts and destroyed when the task stops. Docker volumes that are `scoped` as shared persist after the task stops.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">autoprovision<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If this value is `true`, the Docker volume is created if it does not already exist. *Note*: This field is only used if the scope is `shared`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">driver<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Docker volume driver to use. The driver value must match the driver name provided by Docker because it is used for task placement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">driver<wbr>Opts<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of Docker driver specific options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">labels<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of custom metadata to add to your Docker volume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scope for the Docker volume, which determines its lifecycle, either `task` or `shared`.  Docker volumes that are scoped to a `task` are automatically provisioned when the task starts and destroyed when the task stops. Docker volumes that are `scoped` as shared persist after the task stops.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">autoprovision<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If this value is `true`, the Docker volume is created if it does not already exist. *Note*: This field is only used if the scope is `shared`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">driver<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Docker volume driver to use. The driver value must match the driver name provided by Docker because it is used for task placement.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">driver<wbr>Opts<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of Docker driver specific options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">labels<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of custom metadata to add to your Docker volume.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The scope for the Docker volume, which determines its lifecycle, either `task` or `shared`.  Docker volumes that are scoped to a `task` are automatically provisioned when the task starts and destroyed when the task stops. Docker volumes that are `scoped` as shared persist after the task stops.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TaskDefinitionVolumeEfsVolumeConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TaskDefinitionVolumeEfsVolumeConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TaskDefinitionVolumeEfsVolumeConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionVolumeEfsVolumeConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#TaskDefinitionVolumeEfsVolumeConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionVolumeEfsVolumeConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.TaskDefinitionVolumeEfsVolumeConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">File<wbr>System<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The path to mount on the host
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">File<wbr>System<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The path to mount on the host
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">file<wbr>System<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The path to mount on the host
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">file_<wbr>system_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path to mount on the host
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "Service"
block_external_search_index: true
---

> **Note:** To prevent a race condition during service deletion, make sure to set `depends_on` to the related `aws.iam.RolePolicy`; otherwise, the policy may be destroyed too soon and the ECS service will then get stuck in the `DRAINING` state.

Provides an ECS service - effectively a task that is expected to run until an error occurs or a user terminates it (typically a webserver or a database).

See [ECS Services section in AWS developer guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs_services.html).

## Example Usage

### Ignoring Changes to Desired Count

You can utilize the generic this provider resource [lifecycle configuration block](https://www.terraform.io/docs/configuration/resources.html#lifecycle) with `ignore_changes` to create an ECS service with an initial count of running instances, then ignore any changes to that count caused externally (e.g. Application Autoscaling).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ecs.Service("example", {
    // Example: Create service with 2 instances to start
    desiredCount: 2,
}, {ignoreChanges: ["desiredCount"]});
```

### Daemon Scheduling Strategy

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bar = new aws.ecs.Service("bar", {
    cluster: aws_ecs_cluster_foo.id,
    schedulingStrategy: "DAEMON",
    taskDefinition: aws_ecs_task_definition_bar.arn,
});
```

## capacity_provider_strategy

The `capacity_provider_strategy` configuration block supports the following:

* `capacity_provider` - (Required) The short name or full Amazon Resource Name (ARN) of the capacity provider.
* `weight` - (Required) The relative percentage of the total number of launched tasks that should use the specified capacity provider.
* `base` - (Optional) The number of tasks, at a minimum, to run on the specified capacity provider. Only one capacity provider in a capacity provider strategy can have a base defined.

## deployment_controller

The `deployment_controller` configuration block supports the following:

* `type` - (Optional) Type of deployment controller. Valid values: `CODE_DEPLOY`, `ECS`. Default: `ECS`.

## load_balancer

`load_balancer` supports the following:

* `elb_name` - (Required for ELB Classic) The name of the ELB (Classic) to associate with the service.
* `target_group_arn` - (Required for ALB/NLB) The ARN of the Load Balancer target group to associate with the service.
* `container_name` - (Required) The name of the container to associate with the load balancer (as it appears in a container definition).
* `container_port` - (Required) The port on the container to associate with the load balancer.

> **Version note:** Multiple `load_balancer` configuration block support was added in version 2.22.0 of the provider. This allows configuration of [ECS service support for multiple target groups](https://aws.amazon.com/about-aws/whats-new/2019/07/amazon-ecs-services-now-support-multiple-load-balancer-target-groups/).

## ordered_placement_strategy

`ordered_placement_strategy` supports the following:

* `type` - (Required) The type of placement strategy. Must be one of: `binpack`, `random`, or `spread`
* `field` - (Optional) For the `spread` placement strategy, valid values are `instanceId` (or `host`,
 which has the same effect), or any platform or custom attribute that is applied to a container instance.
 For the `binpack` type, valid values are `memory` and `cpu`. For the `random` type, this attribute is not
 needed. For more information, see [Placement Strategy](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_PlacementStrategy.html).

> **Note:** for `spread`, `host` and `instanceId` will be normalized, by AWS, to be `instanceId`. This means the statefile will show `instanceId` but your config will differ if you use `host`.

## placement_constraints

`placement_constraints` support the following:

* `type` - (Required) The type of constraint. The only valid values at this time are `memberOf` and `distinctInstance`.
* `expression` -  (Optional) Cluster Query Language expression to apply to the constraint. Does not need to be specified
for the `distinctInstance` type.
For more information, see [Cluster Query Language in the Amazon EC2 Container
Service Developer
Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-query-language.html).

## network_configuration

`network_configuration` support the following:

* `subnets` - (Required) The subnets associated with the task or service.
* `security_groups` - (Optional) The security groups associated with the task or service. If you do not specify a security group, the default security group for the VPC is used.
* `assign_public_ip` - (Optional) Assign a public IP address to the ENI (Fargate launch type only). Valid values are `true` or `false`. Default `false`.

For more information, see [Task Networking](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-networking.html)

## service_registries

`service_registries` support the following:

* `registry_arn` - (Required) The ARN of the Service Registry. The currently supported service registry is Amazon Route 53 Auto Naming Service(`aws.servicediscovery.Service`). For more information, see [Service](https://docs.aws.amazon.com/Route53/latest/APIReference/API_autonaming_Service.html)
* `port` - (Optional) The port value used if your Service Discovery service specified an SRV record.
* `container_port` - (Optional) The port value, already specified in the task definition, to be used for your service discovery service.
* `container_name` - (Optional) The container name value, already specified in the task definition, to be used for your service discovery service.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ecs_service.html.markdown.



## Create a Service Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#Service">Service</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#ServiceArgs">ServiceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Service</span><span class="p">(resource_name, opts=None, </span>capacity_provider_strategies=None<span class="p">, </span>cluster=None<span class="p">, </span>deployment_controller=None<span class="p">, </span>deployment_maximum_percent=None<span class="p">, </span>deployment_minimum_healthy_percent=None<span class="p">, </span>desired_count=None<span class="p">, </span>enable_ecs_managed_tags=None<span class="p">, </span>health_check_grace_period_seconds=None<span class="p">, </span>iam_role=None<span class="p">, </span>launch_type=None<span class="p">, </span>load_balancers=None<span class="p">, </span>name=None<span class="p">, </span>network_configuration=None<span class="p">, </span>ordered_placement_strategies=None<span class="p">, </span>placement_constraints=None<span class="p">, </span>platform_version=None<span class="p">, </span>propagate_tags=None<span class="p">, </span>scheduling_strategy=None<span class="p">, </span>service_registries=None<span class="p">, </span>tags=None<span class="p">, </span>task_definition=None<span class="p">, </span>wait_for_steady_state=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewService<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceArgs">ServiceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#Service">Service</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.Service.html">Service</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceArgs.html">ServiceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">List&lt;Service<wbr>Capacity<wbr>Provider<wbr>Strategy<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Service<wbr>Deployment<wbr>Controller<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">List&lt;Service<wbr>Load<wbr>Balancer<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Service<wbr>Network<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">List&lt;Service<wbr>Ordered<wbr>Placement<wbr>Strategy<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">List&lt;Service<wbr>Placement<wbr>Constraint<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Service<wbr>Service<wbr>Registries<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">[]Service<wbr>Capacity<wbr>Provider<wbr>Strategy</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">*Service<wbr>Deployment<wbr>Controller</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">[]Service<wbr>Load<wbr>Balancer</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">*Service<wbr>Network<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">[]Service<wbr>Ordered<wbr>Placement<wbr>Strategy</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">[]Service<wbr>Placement<wbr>Constraint</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">*Service<wbr>Service<wbr>Registries</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">Service<wbr>Capacity<wbr>Provider<wbr>Strategy[]?</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Service<wbr>Deployment<wbr>Controller?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">Service<wbr>Load<wbr>Balancer[]?</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Service<wbr>Network<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">Service<wbr>Ordered<wbr>Placement<wbr>Strategy[]?</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">Service<wbr>Placement<wbr>Constraint[]?</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Service<wbr>Service<wbr>Registries?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity_<wbr>provider_<wbr>strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">List[Service<wbr>Capacity<wbr>Provider<wbr>Strategy]</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Dict[Service<wbr>Deployment<wbr>Controller]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>maximum_<wbr>percent<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>minimum_<wbr>healthy_<wbr>percent<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>ecs_<wbr>managed_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>grace_<wbr>period_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">List[Service<wbr>Load<wbr>Balancer]</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Dict[Service<wbr>Network<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered_<wbr>placement_<wbr>strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">List[Service<wbr>Ordered<wbr>Placement<wbr>Strategy]</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">List[Service<wbr>Placement<wbr>Constraint]</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">propagate_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheduling_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Dict[Service<wbr>Service<wbr>Registries]</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">task_<wbr>definition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>steady_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Service Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">List&lt;Service<wbr>Capacity<wbr>Provider<wbr>Strategy&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Service<wbr>Deployment<wbr>Controller?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">List&lt;Service<wbr>Load<wbr>Balancer&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Service<wbr>Network<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">List&lt;Service<wbr>Ordered<wbr>Placement<wbr>Strategy&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">List&lt;Service<wbr>Placement<wbr>Constraint&gt;?</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Service<wbr>Service<wbr>Registries?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">[]Service<wbr>Capacity<wbr>Provider<wbr>Strategy</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">*Service<wbr>Deployment<wbr>Controller</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">[]Service<wbr>Load<wbr>Balancer</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">*Service<wbr>Network<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">[]Service<wbr>Ordered<wbr>Placement<wbr>Strategy</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">[]Service<wbr>Placement<wbr>Constraint</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">*Service<wbr>Service<wbr>Registries</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">Service<wbr>Capacity<wbr>Provider<wbr>Strategy[]?</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Service<wbr>Deployment<wbr>Controller?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">Service<wbr>Load<wbr>Balancer[]?</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Service<wbr>Network<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">Service<wbr>Ordered<wbr>Placement<wbr>Strategy[]?</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">Service<wbr>Placement<wbr>Constraint[]?</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Service<wbr>Service<wbr>Registries?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">capacity_<wbr>provider_<wbr>strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">List[Service<wbr>Capacity<wbr>Provider<wbr>Strategy]</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Dict[Service<wbr>Deployment<wbr>Controller]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>maximum_<wbr>percent<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>minimum_<wbr>healthy_<wbr>percent<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">desired_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>ecs_<wbr>managed_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check_<wbr>grace_<wbr>period_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">List[Service<wbr>Load<wbr>Balancer]</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Dict[Service<wbr>Network<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ordered_<wbr>placement_<wbr>strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">List[Service<wbr>Ordered<wbr>Placement<wbr>Strategy]</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement_<wbr>constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">List[Service<wbr>Placement<wbr>Constraint]</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">propagate_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scheduling_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Dict[Service<wbr>Service<wbr>Registries]</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">task_<wbr>definition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait_<wbr>for_<wbr>steady_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Service Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#ServiceState">ServiceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ecs/#Service">Service</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>capacity_provider_strategies=None<span class="p">, </span>cluster=None<span class="p">, </span>deployment_controller=None<span class="p">, </span>deployment_maximum_percent=None<span class="p">, </span>deployment_minimum_healthy_percent=None<span class="p">, </span>desired_count=None<span class="p">, </span>enable_ecs_managed_tags=None<span class="p">, </span>health_check_grace_period_seconds=None<span class="p">, </span>iam_role=None<span class="p">, </span>launch_type=None<span class="p">, </span>load_balancers=None<span class="p">, </span>name=None<span class="p">, </span>network_configuration=None<span class="p">, </span>ordered_placement_strategies=None<span class="p">, </span>placement_constraints=None<span class="p">, </span>platform_version=None<span class="p">, </span>propagate_tags=None<span class="p">, </span>scheduling_strategy=None<span class="p">, </span>service_registries=None<span class="p">, </span>tags=None<span class="p">, </span>task_definition=None<span class="p">, </span>wait_for_steady_state=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetService<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceState">ServiceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#Service">Service</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.Service.html">Service</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceState.html">ServiceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Service resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">List&lt;Service<wbr>Capacity<wbr>Provider<wbr>Strategy<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Service<wbr>Deployment<wbr>Controller<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">List&lt;Service<wbr>Load<wbr>Balancer<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Service<wbr>Network<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">List&lt;Service<wbr>Ordered<wbr>Placement<wbr>Strategy<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">List&lt;Service<wbr>Placement<wbr>Constraint<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Service<wbr>Service<wbr>Registries<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">[]Service<wbr>Capacity<wbr>Provider<wbr>Strategy</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">*Service<wbr>Deployment<wbr>Controller</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">[]Service<wbr>Load<wbr>Balancer</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">*Service<wbr>Network<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">[]Service<wbr>Ordered<wbr>Placement<wbr>Strategy</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">[]Service<wbr>Placement<wbr>Constraint</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">*Service<wbr>Service<wbr>Registries</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity<wbr>Provider<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">Service<wbr>Capacity<wbr>Provider<wbr>Strategy[]?</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Service<wbr>Deployment<wbr>Controller?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Maximum<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Minimum<wbr>Healthy<wbr>Percent<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Ecs<wbr>Managed<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Grace<wbr>Period<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">Service<wbr>Load<wbr>Balancer[]?</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Service<wbr>Network<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered<wbr>Placement<wbr>Strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">Service<wbr>Ordered<wbr>Placement<wbr>Strategy[]?</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">Service<wbr>Placement<wbr>Constraint[]?</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">propagate<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheduling<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Service<wbr>Service<wbr>Registries?</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task<wbr>Definition<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Steady<wbr>State<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity_<wbr>provider_<wbr>strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicecapacityproviderstrategy">List[Service<wbr>Capacity<wbr>Provider<wbr>Strategy]</a></span>
    </dt>
    <dd>{{% md %}}The capacity provider strategy to use for the service. Can be one or more.  Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of an ECS cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>controller<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicedeploymentcontroller">Dict[Service<wbr>Deployment<wbr>Controller]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing deployment controller configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>maximum_<wbr>percent<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The upper limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that can be running in a service during a deployment. Not valid when using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>minimum_<wbr>healthy_<wbr>percent<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The lower limit (as a percentage of the service&#39;s desiredCount) of the number of running tasks that must remain running and healthy in a service during a deployment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of instances of the task definition to place and keep running. Defaults to 0. Do not specify if using the `DAEMON` scheduling strategy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>ecs_<wbr>managed_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to enable Amazon ECS managed tags for the tasks within the service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>grace_<wbr>period_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Seconds to ignore failing load balancer health checks on newly instantiated tasks to prevent premature shutdown, up to 2147483647. Only valid for services configured to use load balancers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the IAM role that allows Amazon ECS to make calls to your load balancer on your behalf. This parameter is required if you are using a load balancer with your service, but only if your task definition does not use the `awsvpc` network mode. If using `awsvpc` network mode, do not specify this role. If your account has already created the Amazon ECS service-linked role, that role is used by default for your service unless you specify a role here.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The launch type on which to run your service. The valid values are `EC2` and `FARGATE`. Defaults to `EC2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceloadbalancer">List[Service<wbr>Load<wbr>Balancer]</a></span>
    </dt>
    <dd>{{% md %}}A load balancer block. Load balancers documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the service (up to 255 letters, numbers, hyphens, and underscores)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#servicenetworkconfiguration">Dict[Service<wbr>Network<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The network configuration for the service. This parameter is required for task definitions that use the `awsvpc` network mode to receive their own Elastic Network Interface, and it is not supported for other network modes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered_<wbr>placement_<wbr>strategies<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceorderedplacementstrategy">List[Service<wbr>Ordered<wbr>Placement<wbr>Strategy]</a></span>
    </dt>
    <dd>{{% md %}}Service level strategy rules that are taken into consideration during task placement. List from top to bottom in order of precedence. The maximum number of `ordered_placement_strategy` blocks is `5`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceplacementconstraint">List[Service<wbr>Placement<wbr>Constraint]</a></span>
    </dt>
    <dd>{{% md %}}rules that are taken into consideration during task placement. Maximum number of
`placement_constraints` is `10`. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The platform version on which to run your service. Only applicable for `launch_type` set to `FARGATE`. Defaults to `LATEST`. More information about Fargate platform versions can be found in the [AWS ECS User Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform_versions.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">propagate_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether to propagate the tags from the task definition or the service to the tasks. The valid values are `SERVICE` and `TASK_DEFINITION`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scheduling_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The scheduling strategy to use for the service. The valid values are `REPLICA` and `DAEMON`. Defaults to `REPLICA`. Note that [*Fargate tasks do not support the `DAEMON` scheduling strategy*](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>registries<span class="property-indicator"></span>
        <span class="property-type"><a href="#serviceserviceregistries">Dict[Service<wbr>Service<wbr>Registries]</a></span>
    </dt>
    <dd>{{% md %}}The service discovery registries for the service. The maximum number of `service_registries` blocks is `1`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">task_<wbr>definition<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The family and revision (`family:revision`) or full ARN of the task definition that you want to run in your service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>steady_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, this provider will wait for the service to reach a steady state (like [`aws ecs wait services-stable`](https://docs.aws.amazon.com/cli/latest/reference/ecs/wait/services-stable.html)) before continuing. Default `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ServiceCapacityProviderStrategy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServiceCapacityProviderStrategy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServiceCapacityProviderStrategy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceCapacityProviderStrategyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceCapacityProviderStrategyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceCapacityProviderStrategyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceCapacityProviderStrategy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Base<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Capacity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weight<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Base<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Capacity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weight<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">base<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">capacity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weight<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">base<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">capacity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weight<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ServiceDeploymentController
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServiceDeploymentController">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServiceDeploymentController">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceDeploymentControllerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceDeploymentControllerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceDeploymentControllerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceDeploymentController.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ServiceLoadBalancer
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServiceLoadBalancer">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServiceLoadBalancer">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceLoadBalancerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceLoadBalancerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceLoadBalancerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceLoadBalancer.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elb<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elb<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elb<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">container_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elb<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ServiceNetworkConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServiceNetworkConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServiceNetworkConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceNetworkConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceNetworkConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceNetworkConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceNetworkConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Assign<wbr>Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Assign<wbr>Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">assign<wbr>Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">assign<wbr>Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ServiceOrderedPlacementStrategy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServiceOrderedPlacementStrategy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServiceOrderedPlacementStrategy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceOrderedPlacementStrategyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceOrderedPlacementStrategyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceOrderedPlacementStrategyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceOrderedPlacementStrategy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Field<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">field<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">field<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ServicePlacementConstraint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServicePlacementConstraint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServicePlacementConstraint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServicePlacementConstraintArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServicePlacementConstraintOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServicePlacementConstraintArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServicePlacementConstraint.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Expression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">expression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ServiceServiceRegistries
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServiceServiceRegistries">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServiceServiceRegistries">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceServiceRegistriesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ecs?tab=doc#ServiceServiceRegistriesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceServiceRegistriesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ecs.ServiceServiceRegistries.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Registry<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Registry<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">container<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">registry<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">container_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">container<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">registry<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








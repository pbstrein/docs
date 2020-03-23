
---
title: "DeploymentGroup"
block_external_search_index: true
---

Provides a CodeDeploy Deployment Group for a CodeDeploy Application

> **NOTE on blue/green deployments:** When using `green_fleet_provisioning_option` with the `COPY_AUTO_SCALING_GROUP` action, CodeDeploy will create a new ASG with a different name. This ASG is _not_ managed by this provider and will conflict with existing configuration and state. You may want to use a different approach to managing deployments that involve multiple ASG, such as `DISCOVER_EXISTING` with separate blue and green ASG.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleRole = new aws.iam.Role("example", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "",
      "Effect": "Allow",
      "Principal": {
        "Service": "codedeploy.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
`,
});
const aWSCodeDeployRole = new aws.iam.RolePolicyAttachment("AWSCodeDeployRole", {
    policyArn: "arn:aws:iam::aws:policy/service-role/AWSCodeDeployRole",
    role: exampleRole.name,
});
const exampleApplication = new aws.codedeploy.Application("example", {});
const exampleTopic = new aws.sns.Topic("example", {});
const exampleDeploymentGroup = new aws.codedeploy.DeploymentGroup("example", {
    alarmConfiguration: {
        alarms: ["my-alarm-name"],
        enabled: true,
    },
    appName: exampleApplication.name,
    autoRollbackConfiguration: {
        enabled: true,
        events: ["DEPLOYMENT_FAILURE"],
    },
    deploymentGroupName: "example-group",
    ec2TagSets: [{
        ec2TagFilters: [
            {
                key: "filterkey1",
                type: "KEY_AND_VALUE",
                value: "filtervalue",
            },
            {
                key: "filterkey2",
                type: "KEY_AND_VALUE",
                value: "filtervalue",
            },
        ],
    }],
    serviceRoleArn: exampleRole.arn,
    triggerConfigurations: [{
        triggerEvents: ["DeploymentFailure"],
        triggerName: "example-trigger",
        triggerTargetArn: exampleTopic.arn,
    }],
});
```

### Blue Green Deployments with ECS

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleApplication = new aws.codedeploy.Application("example", {
    computePlatform: "ECS",
});
const exampleDeploymentGroup = new aws.codedeploy.DeploymentGroup("example", {
    appName: exampleApplication.name,
    autoRollbackConfiguration: {
        enabled: true,
        events: ["DEPLOYMENT_FAILURE"],
    },
    blueGreenDeploymentConfig: {
        deploymentReadyOption: {
            actionOnTimeout: "CONTINUE_DEPLOYMENT",
        },
        terminateBlueInstancesOnDeploymentSuccess: {
            action: "TERMINATE",
            terminationWaitTimeInMinutes: 5,
        },
    },
    deploymentConfigName: "CodeDeployDefault.ECSAllAtOnce",
    deploymentGroupName: "example",
    deploymentStyle: {
        deploymentOption: "WITH_TRAFFIC_CONTROL",
        deploymentType: "BLUE_GREEN",
    },
    ecsService: {
        clusterName: aws_ecs_cluster_example.name,
        serviceName: aws_ecs_service_example.name,
    },
    loadBalancerInfo: {
        targetGroupPairInfo: {
            prodTrafficRoute: {
                listenerArns: [aws_lb_listener_example.arn],
            },
            targetGroups: [
                {
                    name: aws_lb_target_group_blue.name,
                },
                {
                    name: aws_lb_target_group_green.name,
                },
            ],
        },
    },
    serviceRoleArn: aws_iam_role_example.arn,
});
```

### Blue Green Deployments with Servers and Classic ELB

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleApplication = new aws.codedeploy.Application("example", {});
const exampleDeploymentGroup = new aws.codedeploy.DeploymentGroup("example", {
    appName: exampleApplication.name,
    blueGreenDeploymentConfig: {
        deploymentReadyOption: {
            actionOnTimeout: "STOP_DEPLOYMENT",
            waitTimeInMinutes: 60,
        },
        greenFleetProvisioningOption: {
            action: "DISCOVER_EXISTING",
        },
        terminateBlueInstancesOnDeploymentSuccess: {
            action: "KEEP_ALIVE",
        },
    },
    deploymentGroupName: "example-group",
    deploymentStyle: {
        deploymentOption: "WITH_TRAFFIC_CONTROL",
        deploymentType: "BLUE_GREEN",
    },
    loadBalancerInfo: {
        elbInfos: [{
            name: aws_elb_example.name,
        }],
    },
    serviceRoleArn: aws_iam_role_example.arn,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/codedeploy_deployment_group.html.markdown.



## Create a DeploymentGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentGroup">DeploymentGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentGroupArgs">DeploymentGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DeploymentGroup</span><span class="p">(resource_name, opts=None, </span>alarm_configuration=None<span class="p">, </span>app_name=None<span class="p">, </span>auto_rollback_configuration=None<span class="p">, </span>autoscaling_groups=None<span class="p">, </span>blue_green_deployment_config=None<span class="p">, </span>deployment_config_name=None<span class="p">, </span>deployment_group_name=None<span class="p">, </span>deployment_style=None<span class="p">, </span>ec2_tag_filters=None<span class="p">, </span>ec2_tag_sets=None<span class="p">, </span>ecs_service=None<span class="p">, </span>load_balancer_info=None<span class="p">, </span>on_premises_instance_tag_filters=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>trigger_configurations=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDeploymentGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupArgs">DeploymentGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroup">DeploymentGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroup.html">DeploymentGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupArgs.html">DeploymentGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Deployment<wbr>Group<wbr>Alarm<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">App<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Deployment<wbr>Group<wbr>Deployment<wbr>Style<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Deployment<wbr>Group<wbr>Ecs<wbr>Service<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">List&lt;Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">List&lt;Deployment<wbr>Group<wbr>Trigger<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">*Deployment<wbr>Group<wbr>Alarm<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">App<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">*Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">*Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">*Deployment<wbr>Group<wbr>Deployment<wbr>Style</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">*Deployment<wbr>Group<wbr>Ecs<wbr>Service</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">*Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">[]Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">[]Deployment<wbr>Group<wbr>Trigger<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Deployment<wbr>Group<wbr>Alarm<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">app<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Deployment<wbr>Group<wbr>Deployment<wbr>Style?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set[]?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Deployment<wbr>Group<wbr>Ecs<wbr>Service?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">Deployment<wbr>Group<wbr>Trigger<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alarm_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Dict[Deployment<wbr>Group<wbr>Alarm<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">app_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>rollback_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Dict[Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">blue_<wbr>green_<wbr>deployment_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Dict[Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>config_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">deployment_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Dict[Deployment<wbr>Group<wbr>Deployment<wbr>Style]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2_<wbr>tag_<wbr>sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs_<wbr>service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Dict[Deployment<wbr>Group<wbr>Ecs<wbr>Service]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancer_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Dict[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on_<wbr>premises_<wbr>instance_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">List[Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trigger_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">List[Deployment<wbr>Group<wbr>Trigger<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## DeploymentGroup Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Deployment<wbr>Group<wbr>Alarm<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">App<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Deployment<wbr>Group<wbr>Deployment<wbr>Style?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Deployment<wbr>Group<wbr>Ecs<wbr>Service?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">List&lt;Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter&gt;?</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">List&lt;Deployment<wbr>Group<wbr>Trigger<wbr>Configuration&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">*Deployment<wbr>Group<wbr>Alarm<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">App<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">*Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">*Deployment<wbr>Group<wbr>Deployment<wbr>Style</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">*Deployment<wbr>Group<wbr>Ecs<wbr>Service</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">*Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">[]Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">[]Deployment<wbr>Group<wbr>Trigger<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Deployment<wbr>Group<wbr>Alarm<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">app<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Deployment<wbr>Group<wbr>Deployment<wbr>Style?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set[]?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Deployment<wbr>Group<wbr>Ecs<wbr>Service?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">on<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">Deployment<wbr>Group<wbr>Trigger<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">alarm_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Dict[Deployment<wbr>Group<wbr>Alarm<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">app_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>rollback_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Dict[Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">autoscaling_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">blue_<wbr>green_<wbr>deployment_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Dict[Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>config_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Dict[Deployment<wbr>Group<wbr>Deployment<wbr>Style]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2_<wbr>tag_<wbr>sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ecs_<wbr>service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Dict[Deployment<wbr>Group<wbr>Ecs<wbr>Service]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancer_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Dict[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">on_<wbr>premises_<wbr>instance_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">List[Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">trigger_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">List[Deployment<wbr>Group<wbr>Trigger<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing DeploymentGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentGroupState">DeploymentGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentGroup">DeploymentGroup</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>alarm_configuration=None<span class="p">, </span>app_name=None<span class="p">, </span>auto_rollback_configuration=None<span class="p">, </span>autoscaling_groups=None<span class="p">, </span>blue_green_deployment_config=None<span class="p">, </span>deployment_config_name=None<span class="p">, </span>deployment_group_name=None<span class="p">, </span>deployment_style=None<span class="p">, </span>ec2_tag_filters=None<span class="p">, </span>ec2_tag_sets=None<span class="p">, </span>ecs_service=None<span class="p">, </span>load_balancer_info=None<span class="p">, </span>on_premises_instance_tag_filters=None<span class="p">, </span>service_role_arn=None<span class="p">, </span>trigger_configurations=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDeploymentGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupState">DeploymentGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroup">DeploymentGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroup.html">DeploymentGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupState.html">DeploymentGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing DeploymentGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Deployment<wbr>Group<wbr>Alarm<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">App<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Deployment<wbr>Group<wbr>Deployment<wbr>Style<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Deployment<wbr>Group<wbr>Ecs<wbr>Service<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">List&lt;Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">List&lt;Deployment<wbr>Group<wbr>Trigger<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">*Deployment<wbr>Group<wbr>Alarm<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">App<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">*Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">*Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">*Deployment<wbr>Group<wbr>Deployment<wbr>Style</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">*Deployment<wbr>Group<wbr>Ecs<wbr>Service</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">*Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">[]Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">[]Deployment<wbr>Group<wbr>Trigger<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alarm<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Deployment<wbr>Group<wbr>Alarm<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">app<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Rollback<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">blue<wbr>Green<wbr>Deployment<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Deployment<wbr>Group<wbr>Deployment<wbr>Style?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Tag<wbr>Sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set[]?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs<wbr>Service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Deployment<wbr>Group<wbr>Ecs<wbr>Service?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancer<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trigger<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">Deployment<wbr>Group<wbr>Trigger<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alarm_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupalarmconfiguration">Dict[Deployment<wbr>Group<wbr>Alarm<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of alarms associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">app_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the application.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>rollback_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupautorollbackconfiguration">Dict[Deployment<wbr>Group<wbr>Auto<wbr>Rollback<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the automatic rollback configuration associated with the deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">autoscaling_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Autoscaling groups associated with the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">blue_<wbr>green_<wbr>deployment_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfig">Dict[Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the blue/green deployment options for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>config_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the group&#39;s deployment config. The default is &#34;CodeDeployDefault.OneAtATime&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>style<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupdeploymentstyle">Dict[Deployment<wbr>Group<wbr>Deployment<wbr>Style]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the type of deployment, either in-place or blue/green, you want to run and whether to route deployment traffic behind a load balancer (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagfilter">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2_<wbr>tag_<wbr>sets<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagset">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of Tag filters associated with the deployment group, which are also referred to as tag groups (documented below). See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs_<wbr>service<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupecsservice">Dict[Deployment<wbr>Group<wbr>Ecs<wbr>Service]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the ECS services for a deployment group (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancer_<wbr>info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfo">Dict[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Single configuration block of the load balancer to use in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on_<wbr>premises_<wbr>instance_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouponpremisesinstancetagfilter">List[Deployment<wbr>Group<wbr>On<wbr>Premises<wbr>Instance<wbr>Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}On premise tag filters associated with the group. See the AWS docs for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The service role ARN that allows deployments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trigger_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouptriggerconfiguration">List[Deployment<wbr>Group<wbr>Trigger<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block(s) of the triggers for the deployment group (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DeploymentGroupAlarmConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupAlarmConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupAlarmConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupAlarmConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupAlarmConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupAlarmConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupAlarmConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Alarms<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of alarms configured for the deployment group. _A maximum of 10 alarms can be added to a deployment group_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ignore<wbr>Poll<wbr>Alarm<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a deployment should continue if information about the current state of alarms cannot be retrieved from CloudWatch. The default value is `false`.
* `true`: The deployment will proceed even if alarm status information can&#39;t be retrieved.
* `false`: The deployment will stop if alarm status information can&#39;t be retrieved.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Alarms<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of alarms configured for the deployment group. _A maximum of 10 alarms can be added to a deployment group_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ignore<wbr>Poll<wbr>Alarm<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a deployment should continue if information about the current state of alarms cannot be retrieved from CloudWatch. The default value is `false`.
* `true`: The deployment will proceed even if alarm status information can&#39;t be retrieved.
* `false`: The deployment will stop if alarm status information can&#39;t be retrieved.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alarms<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of alarms configured for the deployment group. _A maximum of 10 alarms can be added to a deployment group_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ignore<wbr>Poll<wbr>Alarm<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a deployment should continue if information about the current state of alarms cannot be retrieved from CloudWatch. The default value is `false`.
* `true`: The deployment will proceed even if alarm status information can&#39;t be retrieved.
* `false`: The deployment will stop if alarm status information can&#39;t be retrieved.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">alarms<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of alarms configured for the deployment group. _A maximum of 10 alarms can be added to a deployment group_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ignore<wbr>Poll<wbr>Alarm<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a deployment should continue if information about the current state of alarms cannot be retrieved from CloudWatch. The default value is `false`.
* `true`: The deployment will proceed even if alarm status information can&#39;t be retrieved.
* `false`: The deployment will stop if alarm status information can&#39;t be retrieved.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupAutoRollbackConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupAutoRollbackConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupAutoRollbackConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupAutoRollbackConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupAutoRollbackConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupAutoRollbackConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupAutoRollbackConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Events<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The event type or types that trigger a rollback. Supported types are `DEPLOYMENT_FAILURE` and `DEPLOYMENT_STOP_ON_ALARM`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Events<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The event type or types that trigger a rollback. Supported types are `DEPLOYMENT_FAILURE` and `DEPLOYMENT_STOP_ON_ALARM`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">events<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The event type or types that trigger a rollback. Supported types are `DEPLOYMENT_FAILURE` and `DEPLOYMENT_STOP_ON_ALARM`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a defined automatic rollback configuration is currently enabled for this Deployment Group. If you enable automatic rollback, you must specify at least one event type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">events<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The event type or types that trigger a rollback. Supported types are `DEPLOYMENT_FAILURE` and `DEPLOYMENT_STOP_ON_ALARM`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupBlueGreenDeploymentConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupBlueGreenDeploymentConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupBlueGreenDeploymentConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Ready<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigdeploymentreadyoption">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Deployment<wbr>Ready<wbr>Option<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about the action to take when newly provisioned instances are ready to receive traffic in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Green<wbr>Fleet<wbr>Provisioning<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfiggreenfleetprovisioningoption">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Green<wbr>Fleet<wbr>Provisioning<wbr>Option<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about how instances are provisioned for a replacement environment in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigterminateblueinstancesondeploymentsuccess">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about whether to terminate instances in the original fleet during a blue/green deployment (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Ready<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigdeploymentreadyoption">*Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Deployment<wbr>Ready<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Information about the action to take when newly provisioned instances are ready to receive traffic in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Green<wbr>Fleet<wbr>Provisioning<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfiggreenfleetprovisioningoption">*Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Green<wbr>Fleet<wbr>Provisioning<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}Information about how instances are provisioned for a replacement environment in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigterminateblueinstancesondeploymentsuccess">*Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success</a></span>
    </dt>
    <dd>{{% md %}}Information about whether to terminate instances in the original fleet during a blue/green deployment (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">deployment<wbr>Ready<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigdeploymentreadyoption">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Deployment<wbr>Ready<wbr>Option?</a></span>
    </dt>
    <dd>{{% md %}}Information about the action to take when newly provisioned instances are ready to receive traffic in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">green<wbr>Fleet<wbr>Provisioning<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfiggreenfleetprovisioningoption">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Green<wbr>Fleet<wbr>Provisioning<wbr>Option?</a></span>
    </dt>
    <dd>{{% md %}}Information about how instances are provisioned for a replacement environment in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigterminateblueinstancesondeploymentsuccess">Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success?</a></span>
    </dt>
    <dd>{{% md %}}Information about whether to terminate instances in the original fleet during a blue/green deployment (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">deployment<wbr>Ready<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigdeploymentreadyoption">Dict[Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Deployment<wbr>Ready<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Information about the action to take when newly provisioned instances are ready to receive traffic in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">green<wbr>Fleet<wbr>Provisioning<wbr>Option<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfiggreenfleetprovisioningoption">Dict[Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Green<wbr>Fleet<wbr>Provisioning<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}Information about how instances are provisioned for a replacement environment in a blue/green deployment (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupbluegreendeploymentconfigterminateblueinstancesondeploymentsuccess">Dict[Deployment<wbr>Group<wbr>Blue<wbr>Green<wbr>Deployment<wbr>Config<wbr>Terminate<wbr>Blue<wbr>Instances<wbr>On<wbr>Deployment<wbr>Success]</a></span>
    </dt>
    <dd>{{% md %}}Information about whether to terminate instances in the original fleet during a blue/green deployment (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigDeploymentReadyOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<wbr>On<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When to reroute traffic from an original environment to a replacement environment in a blue/green deployment.
* `CONTINUE_DEPLOYMENT`: Register new instances with the load balancer immediately after the new application revision is installed on the instances in the replacement environment.
* `STOP_DEPLOYMENT`: Do not register new instances with load balancer unless traffic is rerouted manually. If traffic is not rerouted manually before the end of the specified wait period, the deployment status is changed to Stopped.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait before the status of a blue/green deployment changed to Stopped if rerouting is not started manually. Applies only to the `STOP_DEPLOYMENT` option for `action_on_timeout`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<wbr>On<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When to reroute traffic from an original environment to a replacement environment in a blue/green deployment.
* `CONTINUE_DEPLOYMENT`: Register new instances with the load balancer immediately after the new application revision is installed on the instances in the replacement environment.
* `STOP_DEPLOYMENT`: Do not register new instances with load balancer unless traffic is rerouted manually. If traffic is not rerouted manually before the end of the specified wait period, the deployment status is changed to Stopped.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait before the status of a blue/green deployment changed to Stopped if rerouting is not started manually. Applies only to the `STOP_DEPLOYMENT` option for `action_on_timeout`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<wbr>On<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When to reroute traffic from an original environment to a replacement environment in a blue/green deployment.
* `CONTINUE_DEPLOYMENT`: Register new instances with the load balancer immediately after the new application revision is installed on the instances in the replacement environment.
* `STOP_DEPLOYMENT`: Do not register new instances with load balancer unless traffic is rerouted manually. If traffic is not rerouted manually before the end of the specified wait period, the deployment status is changed to Stopped.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait before the status of a blue/green deployment changed to Stopped if rerouting is not started manually. Applies only to the `STOP_DEPLOYMENT` option for `action_on_timeout`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<wbr>On<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When to reroute traffic from an original environment to a replacement environment in a blue/green deployment.
* `CONTINUE_DEPLOYMENT`: Register new instances with the load balancer immediately after the new application revision is installed on the instances in the replacement environment.
* `STOP_DEPLOYMENT`: Do not register new instances with load balancer unless traffic is rerouted manually. If traffic is not rerouted manually before the end of the specified wait period, the deployment status is changed to Stopped.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait before the status of a blue/green deployment changed to Stopped if rerouting is not started manually. Applies only to the `STOP_DEPLOYMENT` option for `action_on_timeout`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigGreenFleetProvisioningOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccess
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccess">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupBlueGreenDeploymentConfigTerminateBlueInstancesOnDeploymentSuccess.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Termination<wbr>Wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait after a successful blue/green deployment before terminating instances from the original environment.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Termination<wbr>Wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait after a successful blue/green deployment before terminating instances from the original environment.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">termination<wbr>Wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait after a successful blue/green deployment before terminating instances from the original environment.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take on instances in the original environment after a successful blue/green deployment.
* `TERMINATE`: Instances are terminated after a specified wait time.
* `KEEP_ALIVE`: Instances are left running after they are deregistered from the load balancer and removed from the deployment group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">termination<wbr>Wait<wbr>Time<wbr>In<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of minutes to wait after a successful blue/green deployment before terminating instances from the original environment.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupDeploymentStyle
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupDeploymentStyle">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupDeploymentStyle">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupDeploymentStyleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupDeploymentStyleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupDeploymentStyleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupDeploymentStyle.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to route deployment traffic behind a load balancer. Valid Values are `WITH_TRAFFIC_CONTROL` or `WITHOUT_TRAFFIC_CONTROL`. Default is `WITHOUT_TRAFFIC_CONTROL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to run an in-place deployment or a blue/green deployment. Valid Values are `IN_PLACE` or `BLUE_GREEN`. Default is `IN_PLACE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to route deployment traffic behind a load balancer. Valid Values are `WITH_TRAFFIC_CONTROL` or `WITHOUT_TRAFFIC_CONTROL`. Default is `WITHOUT_TRAFFIC_CONTROL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to run an in-place deployment or a blue/green deployment. Valid Values are `IN_PLACE` or `BLUE_GREEN`. Default is `IN_PLACE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">deployment<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to route deployment traffic behind a load balancer. Valid Values are `WITH_TRAFFIC_CONTROL` or `WITHOUT_TRAFFIC_CONTROL`. Default is `WITHOUT_TRAFFIC_CONTROL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to run an in-place deployment or a blue/green deployment. Valid Values are `IN_PLACE` or `BLUE_GREEN`. Default is `IN_PLACE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">deployment<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether to route deployment traffic behind a load balancer. Valid Values are `WITH_TRAFFIC_CONTROL` or `WITHOUT_TRAFFIC_CONTROL`. Default is `WITHOUT_TRAFFIC_CONTROL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether to run an in-place deployment or a blue/green deployment. Valid Values are `IN_PLACE` or `BLUE_GREEN`. Default is `IN_PLACE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupEc2TagFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupEc2TagFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupEc2TagFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEc2TagFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEc2TagFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEc2TagFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEc2TagFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupEc2TagSet
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupEc2TagSet">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupEc2TagSet">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEc2TagSetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEc2TagSetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEc2TagSetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEc2TagSet.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagsetec2tagfilter">List&lt;Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set<wbr>Ec2Tag<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagsetec2tagfilter">[]Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set<wbr>Ec2Tag<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ec2Tag<wbr>Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagsetec2tagfilter">Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set<wbr>Ec2Tag<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ec2_<wbr>tag_<wbr>filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgroupec2tagsetec2tagfilter">List[Deployment<wbr>Group<wbr>Ec2Tag<wbr>Set<wbr>Ec2Tag<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Tag filters associated with the deployment group. See the AWS docs for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupEc2TagSetEc2TagFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupEc2TagSetEc2TagFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupEc2TagSetEc2TagFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEc2TagSetEc2TagFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEc2TagSetEc2TagFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEc2TagSetEc2TagFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEc2TagSetEc2TagFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupEcsService
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupEcsService">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupEcsService">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEcsServiceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupEcsServiceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEcsServiceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupEcsService.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ECS cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ECS service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ECS cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ECS service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ECS cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ECS service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the ECS cluster.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the ECS service.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Elb<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfoelbinfo">List&lt;Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Elb<wbr>Info<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The Classic Elastic Load Balancer to use in a deployment. Conflicts with `target_group_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgroupinfo">List&lt;Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Info<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group to use in a deployment. Conflicts with `elb_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Pair<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group pair to use in a deployment. Conflicts with `elb_info` and `target_group_info`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Elb<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfoelbinfo">[]Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Elb<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}The Classic Elastic Load Balancer to use in a deployment. Conflicts with `target_group_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgroupinfo">[]Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group to use in a deployment. Conflicts with `elb_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Pair<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfo">*Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group pair to use in a deployment. Conflicts with `elb_info` and `target_group_info`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">elb<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfoelbinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Elb<wbr>Info[]?</a></span>
    </dt>
    <dd>{{% md %}}The Classic Elastic Load Balancer to use in a deployment. Conflicts with `target_group_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgroupinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Info[]?</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group to use in a deployment. Conflicts with `elb_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Pair<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfo">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group pair to use in a deployment. Conflicts with `elb_info` and `target_group_info`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">elb<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfoelbinfo">List[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Elb<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}The Classic Elastic Load Balancer to use in a deployment. Conflicts with `target_group_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Infos<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgroupinfo">List[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group to use in a deployment. Conflicts with `elb_info` and `target_group_pair_info`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Pair<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfo">Dict[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}The (Application/Network Load Balancer) target group pair to use in a deployment. Conflicts with `elb_info` and `target_group_info`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfoElbInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfoElbInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfoElbInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoElbInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoElbInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoElbInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoElbInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfoTargetGroupInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfoTargetGroupInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfoTargetGroupInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfoTargetGroupPairInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Prod<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfoprodtrafficroute">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Prod<wbr>Traffic<wbr>Route<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the production traffic route (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotargetgroup">List&lt;Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Target<wbr>Group<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Configuration blocks for a target group within a target group pair (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Test<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotesttrafficroute">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Test<wbr>Traffic<wbr>Route<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the test traffic route (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Prod<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfoprodtrafficroute">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Prod<wbr>Traffic<wbr>Route</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the production traffic route (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotargetgroup">[]Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Target<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}Configuration blocks for a target group within a target group pair (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Test<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotesttrafficroute">*Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Test<wbr>Traffic<wbr>Route</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the test traffic route (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">prod<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfoprodtrafficroute">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Prod<wbr>Traffic<wbr>Route</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the production traffic route (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotargetgroup">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Target<wbr>Group[]</a></span>
    </dt>
    <dd>{{% md %}}Configuration blocks for a target group within a target group pair (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">test<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotesttrafficroute">Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Test<wbr>Traffic<wbr>Route?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the test traffic route (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">prod<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfoprodtrafficroute">Dict[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Prod<wbr>Traffic<wbr>Route]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the production traffic route (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotargetgroup">List[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Target<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}Configuration blocks for a target group within a target group pair (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">test<wbr>Traffic<wbr>Route<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentgrouploadbalancerinfotargetgrouppairinfotesttrafficroute">Dict[Deployment<wbr>Group<wbr>Load<wbr>Balancer<wbr>Info<wbr>Target<wbr>Group<wbr>Pair<wbr>Info<wbr>Test<wbr>Traffic<wbr>Route]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for the test traffic route (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRoute
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRoute">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRoute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRouteArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRouteOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRouteArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoProdTrafficRoute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroup
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroup">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroup">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroupArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroupOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroupArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTargetGroup.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the target group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRoute
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRoute">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRoute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRouteArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRouteOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRouteArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupLoadBalancerInfoTargetGroupPairInfoTestTrafficRoute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">listener<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the load balancer listeners.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupOnPremisesInstanceTagFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupOnPremisesInstanceTagFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupOnPremisesInstanceTagFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupOnPremisesInstanceTagFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupOnPremisesInstanceTagFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupOnPremisesInstanceTagFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupOnPremisesInstanceTagFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key of the tag filter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the tag filter, either `KEY_ONLY`, `VALUE_ONLY`, or `KEY_AND_VALUE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the tag filter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentGroupTriggerConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentGroupTriggerConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentGroupTriggerConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupTriggerConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentGroupTriggerConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupTriggerConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentGroupTriggerConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Trigger<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The event type or types for which notifications are triggered. Some values that are supported: `DeploymentStart`, `DeploymentSuccess`, `DeploymentFailure`, `DeploymentStop`, `DeploymentRollback`, `InstanceStart`, `InstanceSuccess`, `InstanceFailure`.  See [the CodeDeploy documentation][1] for all possible values.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Trigger<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the notification trigger.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Trigger<wbr>Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic through which notifications are sent.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Trigger<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The event type or types for which notifications are triggered. Some values that are supported: `DeploymentStart`, `DeploymentSuccess`, `DeploymentFailure`, `DeploymentStop`, `DeploymentRollback`, `InstanceStart`, `InstanceSuccess`, `InstanceFailure`.  See [the CodeDeploy documentation][1] for all possible values.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Trigger<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the notification trigger.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Trigger<wbr>Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic through which notifications are sent.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">trigger<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The event type or types for which notifications are triggered. Some values that are supported: `DeploymentStart`, `DeploymentSuccess`, `DeploymentFailure`, `DeploymentStop`, `DeploymentRollback`, `InstanceStart`, `InstanceSuccess`, `InstanceFailure`.  See [the CodeDeploy documentation][1] for all possible values.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">trigger<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the notification trigger.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">trigger<wbr>Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic through which notifications are sent.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">trigger<wbr>Events<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The event type or types for which notifications are triggered. Some values that are supported: `DeploymentStart`, `DeploymentSuccess`, `DeploymentFailure`, `DeploymentStop`, `DeploymentRollback`, `InstanceStart`, `InstanceSuccess`, `InstanceFailure`.  See [the CodeDeploy documentation][1] for all possible values.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">trigger<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the notification trigger.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">trigger<wbr>Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the SNS topic through which notifications are sent.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








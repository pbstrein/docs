
---
title: "DeploymentConfig"
block_external_search_index: true
---

Provides a CodeDeploy deployment config for an application

## Example Usage

### Server Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const fooDeploymentConfig = new aws.codedeploy.DeploymentConfig("foo", {
    deploymentConfigName: "test-deployment-config",
    minimumHealthyHosts: {
        type: "HOST_COUNT",
        value: 2,
    },
});
const fooDeploymentGroup = new aws.codedeploy.DeploymentGroup("foo", {
    alarmConfiguration: {
        alarms: ["my-alarm-name"],
        enabled: true,
    },
    appName: aws_codedeploy_app_foo_app.name,
    autoRollbackConfiguration: {
        enabled: true,
        events: ["DEPLOYMENT_FAILURE"],
    },
    deploymentConfigName: fooDeploymentConfig.id,
    deploymentGroupName: "bar",
    ec2TagFilters: [{
        key: "filterkey",
        type: "KEY_AND_VALUE",
        value: "filtervalue",
    }],
    serviceRoleArn: aws_iam_role_foo_role.arn,
    triggerConfigurations: [{
        triggerEvents: ["DeploymentFailure"],
        triggerName: "foo-trigger",
        triggerTargetArn: "foo-topic-arn",
    }],
});
```

### Lambda Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const fooDeploymentConfig = new aws.codedeploy.DeploymentConfig("foo", {
    computePlatform: "Lambda",
    deploymentConfigName: "test-deployment-config",
    trafficRoutingConfig: {
        timeBasedLinear: {
            interval: 10,
            percentage: 10,
        },
        type: "TimeBasedLinear",
    },
});
const fooDeploymentGroup = new aws.codedeploy.DeploymentGroup("foo", {
    alarmConfiguration: {
        alarms: ["my-alarm-name"],
        enabled: true,
    },
    appName: aws_codedeploy_app_foo_app.name,
    autoRollbackConfiguration: {
        enabled: true,
        events: ["DEPLOYMENT_STOP_ON_ALARM"],
    },
    deploymentConfigName: fooDeploymentConfig.id,
    deploymentGroupName: "bar",
    serviceRoleArn: aws_iam_role_foo_role.arn,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/codedeploy_deployment_config.html.markdown.



## Create a DeploymentConfig Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentConfig">DeploymentConfig</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentConfigArgs">DeploymentConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DeploymentConfig</span><span class="p">(resource_name, opts=None, </span>compute_platform=None<span class="p">, </span>deployment_config_name=None<span class="p">, </span>minimum_healthy_hosts=None<span class="p">, </span>traffic_routing_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDeploymentConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigArgs">DeploymentConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfig">DeploymentConfig</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfig.html">DeploymentConfig</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigArgs.html">DeploymentConfigArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">*Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">*Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts?</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compute_<wbr>platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">deployment_<wbr>config_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum_<wbr>healthy_<wbr>hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Dict[Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts]</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>routing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Dict[Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## DeploymentConfig Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Config<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts?</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Config<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">*Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">*Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Config<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-"
            title="">minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts?</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">compute_<wbr>platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>config_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>config_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-"
            title="">minimum_<wbr>healthy_<wbr>hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Dict[Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts]</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic_<wbr>routing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Dict[Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing DeploymentConfig Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentConfigState">DeploymentConfigState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codedeploy/#DeploymentConfig">DeploymentConfig</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>compute_platform=None<span class="p">, </span>deployment_config_id=None<span class="p">, </span>deployment_config_name=None<span class="p">, </span>minimum_healthy_hosts=None<span class="p">, </span>traffic_routing_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDeploymentConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigState">DeploymentConfigState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfig">DeploymentConfig</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfig.html">DeploymentConfig</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigState.html">DeploymentConfigState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing DeploymentConfig resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">*Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">*Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compute<wbr>Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Config<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Config<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum<wbr>Healthy<wbr>Hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts?</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compute_<wbr>platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute platform can be `Server`, `Lambda`, or `ECS`. Default is `Server`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>config_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Assigned deployment config id
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>config_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the deployment config.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum_<wbr>healthy_<wbr>hosts<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigminimumhealthyhosts">Dict[Deployment<wbr>Config<wbr>Minimum<wbr>Healthy<wbr>Hosts]</a></span>
    </dt>
    <dd>{{% md %}}A minimum_healthy_hosts block. Required for `Server` compute platform. Minimum Healthy Hosts are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>routing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfig">Dict[Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}A traffic_routing_config block. Traffic Routing Config is documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DeploymentConfigMinimumHealthyHosts
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentConfigMinimumHealthyHosts">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentConfigMinimumHealthyHosts">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigMinimumHealthyHostsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigMinimumHealthyHostsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigMinimumHealthyHostsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigMinimumHealthyHosts.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">int?</span>
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

    <dt class="property-optional"
            title="Optional">Value<span class="property-indicator"></span>
        <span class="property-type">*int</span>
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

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">number?</span>
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

    <dt class="property-optional"
            title="Optional">value<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentConfigTrafficRoutingConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentConfigTrafficRoutingConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentConfigTrafficRoutingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigTrafficRoutingConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigTrafficRoutingConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigTrafficRoutingConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigTrafficRoutingConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Time<wbr>Based<wbr>Canary<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedcanary">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Canary<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Time<wbr>Based<wbr>Linear<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedlinear">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Linear<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
            title="Optional">Time<wbr>Based<wbr>Canary<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedcanary">*Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Canary</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Time<wbr>Based<wbr>Linear<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedlinear">*Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Linear</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
            title="Optional">time<wbr>Based<wbr>Canary<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedcanary">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Canary?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">time<wbr>Based<wbr>Linear<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedlinear">Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Linear?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
            title="Optional">time<wbr>Based<wbr>Canary<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedcanary">Dict[Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Canary]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">time<wbr>Based<wbr>Linear<span class="property-indicator"></span>
        <span class="property-type"><a href="#deploymentconfigtrafficroutingconfigtimebasedlinear">Dict[Deployment<wbr>Config<wbr>Traffic<wbr>Routing<wbr>Config<wbr>Time<wbr>Based<wbr>Linear]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentConfigTrafficRoutingConfigTimeBasedCanary
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentConfigTrafficRoutingConfigTimeBasedCanary">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentConfigTrafficRoutingConfigTimeBasedCanary">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigTrafficRoutingConfigTimeBasedCanaryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigTrafficRoutingConfigTimeBasedCanaryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigTrafficRoutingConfigTimeBasedCanaryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigTrafficRoutingConfigTimeBasedCanary.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Percentage<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Percentage<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">percentage<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">percentage<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DeploymentConfigTrafficRoutingConfigTimeBasedLinear
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DeploymentConfigTrafficRoutingConfigTimeBasedLinear">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DeploymentConfigTrafficRoutingConfigTimeBasedLinear">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigTrafficRoutingConfigTimeBasedLinearArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codedeploy?tab=doc#DeploymentConfigTrafficRoutingConfigTimeBasedLinearOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigTrafficRoutingConfigTimeBasedLinearArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codedeploy.DeploymentConfigTrafficRoutingConfigTimeBasedLinear.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Percentage<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Percentage<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">percentage<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">percentage<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "Broker"
block_external_search_index: true
---

Provides an MQ Broker Resource. This resources also manages users for the broker.

For more information on Amazon MQ, see [Amazon MQ documentation](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/welcome.html).

Changes to an MQ Broker can occur when you change a
parameter, such as `configuration` or `user`, and are reflected in the next maintenance
window. Because of this, this provider may report a difference in its planning
phase because a modification has not yet taken place. You can use the
`apply_immediately` flag to instruct the service to apply the change immediately
(see documentation below).

> **Note:** using `apply_immediately` can result in a
brief downtime as the broker reboots.

> **Note:** All arguments including the username and password will be stored in the raw state as plain-text.
[Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.mq.Broker("example", {
    brokerName: "example",
    configuration: {
        id: aws_mq_configuration_test.id,
        revision: aws_mq_configuration_test.latestRevision,
    },
    engineType: "ActiveMQ",
    engineVersion: "5.15.0",
    hostInstanceType: "mq.t2.micro",
    securityGroups: [aws_security_group_test.id],
    users: [{
        password: "MindTheGap",
        username: "ExampleUser",
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/mq_broker.html.markdown.



## Create a Broker Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/mq/#Broker">Broker</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/mq/#BrokerArgs">BrokerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Broker</span><span class="p">(resource_name, opts=None, </span>apply_immediately=None<span class="p">, </span>auto_minor_version_upgrade=None<span class="p">, </span>broker_name=None<span class="p">, </span>configuration=None<span class="p">, </span>deployment_mode=None<span class="p">, </span>encryption_options=None<span class="p">, </span>engine_type=None<span class="p">, </span>engine_version=None<span class="p">, </span>host_instance_type=None<span class="p">, </span>logs=None<span class="p">, </span>maintenance_window_start_time=None<span class="p">, </span>publicly_accessible=None<span class="p">, </span>security_groups=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>users=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBroker<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerArgs">BrokerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#Broker">Broker</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.Broker.html">Broker</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerArgs.html">BrokerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Broker<wbr>Encryption<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Broker<wbr>Logs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">List&lt;Broker<wbr>User<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">*Broker<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">*Broker<wbr>Encryption<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">*Broker<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">*Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">[]Broker<wbr>User</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Broker<wbr>Encryption<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Broker<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time?</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">Broker<wbr>User[]</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">broker_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Dict[Broker<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Dict[Broker<wbr>Encryption<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">engine_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">host_<wbr>instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Dict[Broker<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance_<wbr>window_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Dict[Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time]</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">List[Broker<wbr>User]</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Broker Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Broker<wbr>Encryption<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">List&lt;Broker<wbr>Instance&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Broker<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">List&lt;Broker<wbr>User&gt;</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">*Broker<wbr>Encryption<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">[]Broker<wbr>Instance</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">*Broker<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">[]Broker<wbr>User</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Broker<wbr>Encryption<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-"
            title="">instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">Broker<wbr>Instance[]</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-"
            title="">logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Broker<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">Broker<wbr>User[]</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">broker_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Dict[Broker<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deployment_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encryption_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Dict[Broker<wbr>Encryption<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host_<wbr>instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-"
            title="">instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">List[Broker<wbr>Instance]</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-"
            title="">logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Dict[Broker<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maintenance_<wbr>window_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Dict[Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time]</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">List[Broker<wbr>User]</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Broker Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/mq/#BrokerState">BrokerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/mq/#Broker">Broker</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>apply_immediately=None<span class="p">, </span>arn=None<span class="p">, </span>auto_minor_version_upgrade=None<span class="p">, </span>broker_name=None<span class="p">, </span>configuration=None<span class="p">, </span>deployment_mode=None<span class="p">, </span>encryption_options=None<span class="p">, </span>engine_type=None<span class="p">, </span>engine_version=None<span class="p">, </span>host_instance_type=None<span class="p">, </span>instances=None<span class="p">, </span>logs=None<span class="p">, </span>maintenance_window_start_time=None<span class="p">, </span>publicly_accessible=None<span class="p">, </span>security_groups=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>users=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBroker<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerState">BrokerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#Broker">Broker</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.Broker.html">Broker</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerState.html">BrokerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Broker resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Broker<wbr>Encryption<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">List&lt;Broker<wbr>Instance<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Broker<wbr>Logs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">List&lt;Broker<wbr>User<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">*Broker<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">*Broker<wbr>Encryption<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">[]Broker<wbr>Instance</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">*Broker<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">*Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">[]Broker<wbr>User</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">broker<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Broker<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Broker<wbr>Encryption<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">Broker<wbr>Instance[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Broker<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance<wbr>Window<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time?</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">Broker<wbr>User[]?</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any broker modifications
are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables automatic upgrades to new minor versions for brokers, as Apache releases the versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">broker_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerconfiguration">Dict[Broker<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deployment_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The deployment mode of the broker. Supported: `SINGLE_INSTANCE` and `ACTIVE_STANDBY_MULTI_AZ`. Defaults to `SINGLE_INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerencryptionoptions">Dict[Broker<wbr>Encryption<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing encryption options. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of broker engine. Currently, Amazon MQ supports only `ActiveMQ`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the broker engine. See the [AmazonMQ Broker Engine docs](https://docs.aws.amazon.com/amazon-mq/latest/developer-guide/broker-engine.html) for supported versions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The broker&#39;s instance type. e.g. `mq.t2.micro` or `mq.m4.large`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerinstance">List[Broker<wbr>Instance]</a></span>
    </dt>
    <dd>{{% md %}}A list of information about allocated brokers (both active &amp; standby).
* `instances.0.console_url` - The URL of the broker&#39;s [ActiveMQ Web Console](http://activemq.apache.org/web-console.html).
* `instances.0.ip_address` - The IP Address of the broker.
* `instances.0.endpoints` - The broker&#39;s wire-level protocol endpoints in the following order &amp; format referenceable e.g. as `instances.0.endpoints.0` (SSL):
* `ssl://broker-id.mq.us-west-2.amazonaws.com:61617`
* `amqp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:5671`
* `stomp&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:61614`
* `mqtt&#43;ssl://broker-id.mq.us-west-2.amazonaws.com:8883`
* `wss://broker-id.mq.us-west-2.amazonaws.com:61619`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokerlogs">Dict[Broker<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}Logging configuration of the broker. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance_<wbr>window_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokermaintenancewindowstarttime">Dict[Broker<wbr>Maintenance<wbr>Window<wbr>Start<wbr>Time]</a></span>
    </dt>
    <dd>{{% md %}}Maintenance window start time. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable connections from applications outside of the VPC that hosts the broker&#39;s subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of security group IDs assigned to the broker.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of subnet IDs in which to launch the broker. A `SINGLE_INSTANCE` deployment requires one subnet. An `ACTIVE_STANDBY_MULTI_AZ` deployment requires two subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">users<span class="property-indicator"></span>
        <span class="property-type"><a href="#brokeruser">List[Broker<wbr>User]</a></span>
    </dt>
    <dd>{{% md %}}The list of all ActiveMQ usernames for the specified broker. See below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### BrokerConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BrokerConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BrokerConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Configuration ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revision<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Revision of the Configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Configuration ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revision<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Revision of the Configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Configuration ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revision<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Revision of the Configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Configuration ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revision<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Revision of the Configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BrokerEncryptionOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BrokerEncryptionOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BrokerEncryptionOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerEncryptionOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerEncryptionOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerEncryptionOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerEncryptionOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Key Management Service (KMS) Customer Master Key (CMK) to use for encryption at rest. Requires setting `use_aws_owned_key` to `false`. To perform drift detection when AWS managed CMKs or customer managed CMKs are in use, this value must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Aws<wbr>Owned<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable an AWS owned Key Management Service (KMS) Customer Master Key (CMK) that is not in your account. Defaults to `true`. Setting to `false` without configuring `kms_key_id` will create an AWS managed Customer Master Key (CMK) aliased to `aws/mq` in your account.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Key Management Service (KMS) Customer Master Key (CMK) to use for encryption at rest. Requires setting `use_aws_owned_key` to `false`. To perform drift detection when AWS managed CMKs or customer managed CMKs are in use, this value must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Use<wbr>Aws<wbr>Owned<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable an AWS owned Key Management Service (KMS) Customer Master Key (CMK) that is not in your account. Defaults to `true`. Setting to `false` without configuring `kms_key_id` will create an AWS managed Customer Master Key (CMK) aliased to `aws/mq` in your account.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Key Management Service (KMS) Customer Master Key (CMK) to use for encryption at rest. Requires setting `use_aws_owned_key` to `false`. To perform drift detection when AWS managed CMKs or customer managed CMKs are in use, this value must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Aws<wbr>Owned<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable an AWS owned Key Management Service (KMS) Customer Master Key (CMK) that is not in your account. Defaults to `true`. Setting to `false` without configuring `kms_key_id` will create an AWS managed Customer Master Key (CMK) aliased to `aws/mq` in your account.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Key Management Service (KMS) Customer Master Key (CMK) to use for encryption at rest. Requires setting `use_aws_owned_key` to `false`. To perform drift detection when AWS managed CMKs or customer managed CMKs are in use, this value must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">use<wbr>Aws<wbr>Owned<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable an AWS owned Key Management Service (KMS) Customer Master Key (CMK) that is not in your account. Defaults to `true`. Setting to `false` without configuring `kms_key_id` will create an AWS managed Customer Master Key (CMK) aliased to `aws/mq` in your account.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BrokerInstance
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BrokerInstance">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerInstanceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerInstance.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Console<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoints<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Console<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoints<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">console<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoints<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">console<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoints<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BrokerLogs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BrokerLogs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BrokerLogs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerLogsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerLogsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerLogsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerLogs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Audit<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables audit logging. User management action made using JMX or the ActiveMQ Web Console is logged. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">General<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables general logging via CloudWatch. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Audit<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables audit logging. User management action made using JMX or the ActiveMQ Web Console is logged. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">General<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables general logging via CloudWatch. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audit<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables audit logging. User management action made using JMX or the ActiveMQ Web Console is logged. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">general<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables general logging via CloudWatch. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audit<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables audit logging. User management action made using JMX or the ActiveMQ Web Console is logged. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">general<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables general logging via CloudWatch. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BrokerMaintenanceWindowStartTime
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BrokerMaintenanceWindowStartTime">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BrokerMaintenanceWindowStartTime">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerMaintenanceWindowStartTimeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerMaintenanceWindowStartTimeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerMaintenanceWindowStartTimeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerMaintenanceWindowStartTime.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Day<wbr>Of<wbr>Week<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The day of the week. e.g. `MONDAY`, `TUESDAY`, or `WEDNESDAY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Time<wbr>Of<wbr>Day<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time, in 24-hour format. e.g. `02:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Time<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time zone, UTC by default, in either the Country/City format, or the UTC offset format. e.g. `CET`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Day<wbr>Of<wbr>Week<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The day of the week. e.g. `MONDAY`, `TUESDAY`, or `WEDNESDAY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Time<wbr>Of<wbr>Day<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time, in 24-hour format. e.g. `02:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Time<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time zone, UTC by default, in either the Country/City format, or the UTC offset format. e.g. `CET`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">day<wbr>Of<wbr>Week<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The day of the week. e.g. `MONDAY`, `TUESDAY`, or `WEDNESDAY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">time<wbr>Of<wbr>Day<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time, in 24-hour format. e.g. `02:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">time<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time zone, UTC by default, in either the Country/City format, or the UTC offset format. e.g. `CET`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">day<wbr>Of<wbr>Week<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The day of the week. e.g. `MONDAY`, `TUESDAY`, or `WEDNESDAY`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">time<wbr>Of<wbr>Day<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time, in 24-hour format. e.g. `02:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">time<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time zone, UTC by default, in either the Country/City format, or the UTC offset format. e.g. `CET`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### BrokerUser
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#BrokerUser">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#BrokerUser">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerUserArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/mq?tab=doc#BrokerUserOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerUserArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Mq.BrokerUser.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Console<wbr>Access<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable access to the [ActiveMQ Web Console](http://activemq.apache.org/web-console.html) for the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The list of groups (20 maximum) to which the ActiveMQ user belongs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password of the user. It must be 12 to 250 characters long, at least 4 unique characters, and must not contain commas.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The username of the user.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Console<wbr>Access<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable access to the [ActiveMQ Web Console](http://activemq.apache.org/web-console.html) for the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The list of groups (20 maximum) to which the ActiveMQ user belongs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password of the user. It must be 12 to 250 characters long, at least 4 unique characters, and must not contain commas.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The username of the user.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">console<wbr>Access<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable access to the [ActiveMQ Web Console](http://activemq.apache.org/web-console.html) for the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The list of groups (20 maximum) to which the ActiveMQ user belongs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password of the user. It must be 12 to 250 characters long, at least 4 unique characters, and must not contain commas.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The username of the user.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">console<wbr>Access<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable access to the [ActiveMQ Web Console](http://activemq.apache.org/web-console.html) for the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The list of groups (20 maximum) to which the ActiveMQ user belongs.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password of the user. It must be 12 to 250 characters long, at least 4 unique characters, and must not contain commas.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The username of the user.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








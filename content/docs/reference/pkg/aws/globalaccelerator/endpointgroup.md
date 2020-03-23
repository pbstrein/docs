
---
title: "EndpointGroup"
block_external_search_index: true
---

Provides a Global Accelerator endpoint group.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.globalaccelerator.EndpointGroup("example", {
    endpointConfigurations: [{
        endpointId: aws_lb_example.arn,
        weight: 100,
    }],
    listenerArn: aws_globalaccelerator_listener_example.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/globalaccelerator_endpoint_group.html.markdown.



## Create a EndpointGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/globalaccelerator/#EndpointGroup">EndpointGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/globalaccelerator/#EndpointGroupArgs">EndpointGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">EndpointGroup</span><span class="p">(resource_name, opts=None, </span>endpoint_configurations=None<span class="p">, </span>endpoint_group_region=None<span class="p">, </span>health_check_interval_seconds=None<span class="p">, </span>health_check_path=None<span class="p">, </span>health_check_port=None<span class="p">, </span>health_check_protocol=None<span class="p">, </span>listener_arn=None<span class="p">, </span>threshold_count=None<span class="p">, </span>traffic_dial_percentage=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewEndpointGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/globalaccelerator?tab=doc#EndpointGroupArgs">EndpointGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/globalaccelerator?tab=doc#EndpointGroup">EndpointGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Globalaccelerator.EndpointGroup.html">EndpointGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Globalaccelerator.EndpointGroupArgs.html">EndpointGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">List&lt;Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">[]Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">List[Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>group_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>interval_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">listener_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>dial_<wbr>percentage<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## EndpointGroup Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">List&lt;Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">[]Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-"
            title="">threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">endpoint_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">List[Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint_<wbr>group_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check_<wbr>interval_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check_<wbr>path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check_<wbr>protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">listener_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-"
            title="">threshold_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic_<wbr>dial_<wbr>percentage<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing EndpointGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/globalaccelerator/#EndpointGroupState">EndpointGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/globalaccelerator/#EndpointGroup">EndpointGroup</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>endpoint_configurations=None<span class="p">, </span>endpoint_group_region=None<span class="p">, </span>health_check_interval_seconds=None<span class="p">, </span>health_check_path=None<span class="p">, </span>health_check_port=None<span class="p">, </span>health_check_protocol=None<span class="p">, </span>listener_arn=None<span class="p">, </span>threshold_count=None<span class="p">, </span>traffic_dial_percentage=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetEndpointGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/globalaccelerator?tab=doc#EndpointGroupState">EndpointGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/globalaccelerator?tab=doc#EndpointGroup">EndpointGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Globalaccelerator.EndpointGroup.html">EndpointGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Globalaccelerator.EndpointGroupState.html">EndpointGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing EndpointGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">List&lt;Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">[]Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Group<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Interval<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">listener<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Dial<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#endpointgroupendpointconfiguration">List[Endpoint<wbr>Group<wbr>Endpoint<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The list of endpoint objects. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>group_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the AWS Region where the endpoint group is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>interval_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time—10 seconds or 30 seconds—between each health check for an endpoint. The default value is 30.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the protocol is HTTP/S, then this specifies the path that is the destination for health check targets. The default value is slash (/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default port is the listener port that this endpoint group is associated with. If listener port is a list of ports, Global Accelerator uses the first port in the list.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check_<wbr>protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol that AWS Global Accelerator uses to check the health of endpoints that are part of this endpoint group. The default value is TCP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">listener_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the listener.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threshold_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks required to set the state of a healthy endpoint to unhealthy, or to set an unhealthy endpoint to healthy. The default value is 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>dial_<wbr>percentage<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The percentage of traffic to send to an AWS Region. Additional traffic is distributed to other endpoint groups for this listener. The default value is 100.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### EndpointGroupEndpointConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#EndpointGroupEndpointConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EndpointGroupEndpointConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/globalaccelerator?tab=doc#EndpointGroupEndpointConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/globalaccelerator?tab=doc#EndpointGroupEndpointConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Globalaccelerator.EndpointGroupEndpointConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Globalaccelerator.EndpointGroupEndpointConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An ID for the endpoint. If the endpoint is a Network Load Balancer or Application Load Balancer, this is the Amazon Resource Name (ARN) of the resource. If the endpoint is an Elastic IP address, this is the Elastic IP address allocation ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weight<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The weight associated with the endpoint. When you add weights to endpoints, you configure AWS Global Accelerator to route traffic based on proportions that you specify. 
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An ID for the endpoint. If the endpoint is a Network Load Balancer or Application Load Balancer, this is the Amazon Resource Name (ARN) of the resource. If the endpoint is an Elastic IP address, this is the Elastic IP address allocation ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weight<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The weight associated with the endpoint. When you add weights to endpoints, you configure AWS Global Accelerator to route traffic based on proportions that you specify. 
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An ID for the endpoint. If the endpoint is a Network Load Balancer or Application Load Balancer, this is the Amazon Resource Name (ARN) of the resource. If the endpoint is an Elastic IP address, this is the Elastic IP address allocation ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weight<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The weight associated with the endpoint. When you add weights to endpoints, you configure AWS Global Accelerator to route traffic based on proportions that you specify. 
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An ID for the endpoint. If the endpoint is a Network Load Balancer or Application Load Balancer, this is the Amazon Resource Name (ARN) of the resource. If the endpoint is an Elastic IP address, this is the Elastic IP address allocation ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weight<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The weight associated with the endpoint. When you add weights to endpoints, you configure AWS Global Accelerator to route traffic based on proportions that you specify. 
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








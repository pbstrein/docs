
---
title: "PublicVirtualInterface"
block_external_search_index: true
---

Provides a Direct Connect public virtual interface resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foo = new aws.directconnect.PublicVirtualInterface("foo", {
    addressFamily: "ipv4",
    amazonAddress: "175.45.176.2/30",
    bgpAsn: 65352,
    connectionId: "dxcon-zzzzzzzz",
    customerAddress: "175.45.176.1/30",
    routeFilterPrefixes: [
        "210.52.109.0/24",
        "175.45.176.0/22",
    ],
    vlan: 4094,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/dx_public_virtual_interface.html.markdown.



## Create a PublicVirtualInterface Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#PublicVirtualInterface">PublicVirtualInterface</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#PublicVirtualInterfaceArgs">PublicVirtualInterfaceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">PublicVirtualInterface</span><span class="p">(resource_name, opts=None, </span>address_family=None<span class="p">, </span>amazon_address=None<span class="p">, </span>bgp_asn=None<span class="p">, </span>bgp_auth_key=None<span class="p">, </span>connection_id=None<span class="p">, </span>customer_address=None<span class="p">, </span>name=None<span class="p">, </span>route_filter_prefixes=None<span class="p">, </span>tags=None<span class="p">, </span>vlan=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPublicVirtualInterface<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#PublicVirtualInterfaceArgs">PublicVirtualInterfaceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#PublicVirtualInterface">PublicVirtualInterface</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.PublicVirtualInterface.html">PublicVirtualInterface</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.PublicVirtualInterfaceArgs.html">PublicVirtualInterfaceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vlan<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vlan<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vlan<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">address_<wbr>family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">amazon_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp_<wbr>auth_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">route_<wbr>filter_<wbr>prefixes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vlan<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## PublicVirtualInterface Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Amazon<wbr>Side<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vlan<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Amazon<wbr>Side<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vlan<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">amazon<wbr>Side<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vlan<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">address_<wbr>family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">amazon_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">amazon_<wbr>side_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws_<wbr>device<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bgp_<wbr>auth_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">customer_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">route_<wbr>filter_<wbr>prefixes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vlan<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing PublicVirtualInterface Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#PublicVirtualInterfaceState">PublicVirtualInterfaceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#PublicVirtualInterface">PublicVirtualInterface</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>address_family=None<span class="p">, </span>amazon_address=None<span class="p">, </span>amazon_side_asn=None<span class="p">, </span>arn=None<span class="p">, </span>aws_device=None<span class="p">, </span>bgp_asn=None<span class="p">, </span>bgp_auth_key=None<span class="p">, </span>connection_id=None<span class="p">, </span>customer_address=None<span class="p">, </span>name=None<span class="p">, </span>route_filter_prefixes=None<span class="p">, </span>tags=None<span class="p">, </span>vlan=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPublicVirtualInterface<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#PublicVirtualInterfaceState">PublicVirtualInterfaceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#PublicVirtualInterface">PublicVirtualInterface</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.PublicVirtualInterface.html">PublicVirtualInterface</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.PublicVirtualInterfaceState.html">PublicVirtualInterfaceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing PublicVirtualInterface resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Amazon<wbr>Side<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vlan<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Amazon<wbr>Side<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vlan<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">address<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">amazon<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">amazon<wbr>Side<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp<wbr>Auth<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">route<wbr>Filter<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vlan<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">address_<wbr>family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The address family for the BGP peer. `ipv4 ` or `ipv6`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">amazon_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">amazon_<wbr>side_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws_<wbr>device<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the virtual interface terminates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The autonomous system (AS) number for Border Gateway Protocol (BGP) configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp_<wbr>auth_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authentication key for BGP configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect connection (or LAG) on which to create the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic. Required for IPv4 BGP peers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name for the virtual interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">route_<wbr>filter_<wbr>prefixes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of routes to be advertised to the AWS network in this region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vlan<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The VLAN ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







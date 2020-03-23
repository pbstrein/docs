
---
title: "VpnConnection"
block_external_search_index: true
---

Manages an EC2 VPN connection. These objects can be connected to customer gateways, and allow you to establish tunnels between your network and Amazon.

> **Note:** All arguments including `tunnel1_preshared_key` and `tunnel2_preshared_key` will be stored in the raw state as plain-text.
[Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

> **Note:** The CIDR blocks in the arguments `tunnel1_inside_cidr` and `tunnel2_inside_cidr` must have a prefix of /30 and be a part of a specific range.
[Read more about this in the AWS documentation](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_VpnTunnelOptionsSpecification.html).

## Example Usage

### EC2 Transit Gateway

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleTransitGateway = new aws.ec2transitgateway.TransitGateway("example", {});
const exampleCustomerGateway = new aws.ec2.CustomerGateway("example", {
    bgpAsn: 65000,
    ipAddress: "172.0.0.1",
    type: "ipsec.1",
});
const exampleVpnConnection = new aws.ec2.VpnConnection("example", {
    customerGatewayId: exampleCustomerGateway.id,
    transitGatewayId: exampleTransitGateway.id,
    type: exampleCustomerGateway.type,
});
```

### Virtual Private Gateway

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const vpc = new aws.ec2.Vpc("vpc", {
    cidrBlock: "10.0.0.0/16",
});
const vpnGateway = new aws.ec2.VpnGateway("vpn_gateway", {
    vpcId: vpc.id,
});
const customerGateway = new aws.ec2.CustomerGateway("customer_gateway", {
    bgpAsn: 65000,
    ipAddress: "172.0.0.1",
    type: "ipsec.1",
});
const main = new aws.ec2.VpnConnection("main", {
    customerGatewayId: customerGateway.id,
    staticRoutesOnly: true,
    type: "ipsec.1",
    vpnGatewayId: vpnGateway.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/vpn_connection.html.markdown.



## Create a VpnConnection Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpnConnection">VpnConnection</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpnConnectionArgs">VpnConnectionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">VpnConnection</span><span class="p">(resource_name, opts=None, </span>customer_gateway_id=None<span class="p">, </span>static_routes_only=None<span class="p">, </span>tags=None<span class="p">, </span>transit_gateway_id=None<span class="p">, </span>tunnel1_inside_cidr=None<span class="p">, </span>tunnel1_preshared_key=None<span class="p">, </span>tunnel2_inside_cidr=None<span class="p">, </span>tunnel2_preshared_key=None<span class="p">, </span>type=None<span class="p">, </span>vpn_gateway_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVpnConnection<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpnConnectionArgs">VpnConnectionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpnConnection">VpnConnection</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpnConnection.html">VpnConnection</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpnConnectionArgs.html">VpnConnectionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">customer_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">static_<wbr>routes_<wbr>only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>inside_<wbr>cidr<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>preshared_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>inside_<wbr>cidr<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>preshared_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## VpnConnection Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Customer<wbr>Gateway<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">List&lt;Vpn<wbr>Connection<wbr>Route&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vgw<wbr>Telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">List&lt;Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Customer<wbr>Gateway<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">[]Vpn<wbr>Connection<wbr>Route<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel1Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tunnel2Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vgw<wbr>Telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">[]Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">customer<wbr>Gateway<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-"
            title="">customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">Vpn<wbr>Connection<wbr>Route[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vgw<wbr>Telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">customer_<wbr>gateway_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-"
            title="">customer_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">List[Vpn<wbr>Connection<wbr>Route]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">static_<wbr>routes_<wbr>only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>attachment_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>bgp_<wbr>holdtime<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>cgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>inside_<wbr>cidr<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>preshared_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel1_<wbr>vgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>bgp_<wbr>holdtime<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>cgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>inside_<wbr>cidr<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>preshared_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tunnel2_<wbr>vgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vgw_<wbr>telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">List[Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">vpn_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing VpnConnection Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpnConnectionState">VpnConnectionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpnConnection">VpnConnection</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>customer_gateway_configuration=None<span class="p">, </span>customer_gateway_id=None<span class="p">, </span>routes=None<span class="p">, </span>static_routes_only=None<span class="p">, </span>tags=None<span class="p">, </span>transit_gateway_attachment_id=None<span class="p">, </span>transit_gateway_id=None<span class="p">, </span>tunnel1_address=None<span class="p">, </span>tunnel1_bgp_asn=None<span class="p">, </span>tunnel1_bgp_holdtime=None<span class="p">, </span>tunnel1_cgw_inside_address=None<span class="p">, </span>tunnel1_inside_cidr=None<span class="p">, </span>tunnel1_preshared_key=None<span class="p">, </span>tunnel1_vgw_inside_address=None<span class="p">, </span>tunnel2_address=None<span class="p">, </span>tunnel2_bgp_asn=None<span class="p">, </span>tunnel2_bgp_holdtime=None<span class="p">, </span>tunnel2_cgw_inside_address=None<span class="p">, </span>tunnel2_inside_cidr=None<span class="p">, </span>tunnel2_preshared_key=None<span class="p">, </span>tunnel2_vgw_inside_address=None<span class="p">, </span>type=None<span class="p">, </span>vgw_telemetries=None<span class="p">, </span>vpn_gateway_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVpnConnection<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpnConnectionState">VpnConnectionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpnConnection">VpnConnection</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpnConnection.html">VpnConnection</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpnConnectionState.html">VpnConnectionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing VpnConnection resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Customer<wbr>Gateway<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">List&lt;Vpn<wbr>Connection<wbr>Route<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vgw<wbr>Telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">List&lt;Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Customer<wbr>Gateway<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">[]Vpn<wbr>Connection<wbr>Route<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel1Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tunnel2Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vgw<wbr>Telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">[]Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">customer<wbr>Gateway<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">Vpn<wbr>Connection<wbr>Route[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">static<wbr>Routes<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Bgp<wbr>Asn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Bgp<wbr>Holdtime<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Cgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Inside<wbr>Cidr<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Preshared<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2Vgw<wbr>Inside<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vgw<wbr>Telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">customer_<wbr>gateway_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The configuration information for the VPN connection&#39;s customer gateway (in the native XML format).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the customer gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routes<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionroute">List[Vpn<wbr>Connection<wbr>Route]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">static_<wbr>routes_<wbr>only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the VPN connection uses static routes exclusively. Static routes must be used for devices that don&#39;t support BGP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Tags to apply to the connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>attachment_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When associated with an EC2 Transit Gateway (`transit_gateway_id` argument), the attachment ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>bgp_<wbr>holdtime<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>cgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>inside_<wbr>cidr<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>preshared_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preshared key of the first VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel1_<wbr>vgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the first VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>bgp_<wbr>asn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The bgp asn number of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>bgp_<wbr>holdtime<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The bgp holdtime of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>cgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (Customer Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>inside_<wbr>cidr<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block of the inside IP addresses for the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>preshared_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preshared key of the second VPN tunnel.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tunnel2_<wbr>vgw_<wbr>inside_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 6890 link-local address of the second VPN tunnel (VPN Gateway Side).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of VPN connection. The only type AWS supports at this time is &#34;ipsec.1&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vgw_<wbr>telemetries<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpnconnectionvgwtelemetry">List[Vpn<wbr>Connection<wbr>Vgw<wbr>Telemetry]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Virtual Private Gateway.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### VpnConnectionRoute
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VpnConnectionRoute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpnConnectionRouteTypeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpnConnectionRoute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VpnConnectionVgwTelemetry
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VpnConnectionVgwTelemetry">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpnConnectionVgwTelemetryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpnConnectionVgwTelemetry.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accepted<wbr>Route<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Status<wbr>Change<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Outside<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accepted<wbr>Route<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Status<wbr>Change<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Outside<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepted<wbr>Route<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Status<wbr>Change<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">outside<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepted<wbr>Route<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Status<wbr>Change<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">outside<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








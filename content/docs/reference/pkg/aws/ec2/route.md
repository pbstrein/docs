
---
title: "Route"
block_external_search_index: true
---

Provides a resource to create a routing table entry (a route) in a VPC routing table.

> **NOTE on Route Tables and Routes:** This provider currently
provides both a standalone Route resource and a Route Table resource with routes
defined in-line. At this time you cannot use a Route Table with in-line routes
in conjunction with any Route resources. Doing so will cause
a conflict of rule settings and will overwrite rules.

## Example IPv6 Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const vpc = new aws.ec2.Vpc("vpc", {
    assignGeneratedIpv6CidrBlock: true,
    cidrBlock: "10.1.0.0/16",
});
const egress = new aws.ec2.EgressOnlyInternetGateway("egress", {
    vpcId: vpc.id,
});
const route = new aws.ec2.Route("r", {
    destinationIpv6CidrBlock: "::/0",
    egressOnlyGatewayId: egress.id,
    routeTableId: "rtb-4fbb3ac4",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/route.html.markdown.



## Create a Route Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#Route">Route</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#RouteArgs">RouteArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Route</span><span class="p">(resource_name, opts=None, </span>destination_cidr_block=None<span class="p">, </span>destination_ipv6_cidr_block=None<span class="p">, </span>egress_only_gateway_id=None<span class="p">, </span>gateway_id=None<span class="p">, </span>instance_id=None<span class="p">, </span>nat_gateway_id=None<span class="p">, </span>network_interface_id=None<span class="p">, </span>route_table_id=None<span class="p">, </span>transit_gateway_id=None<span class="p">, </span>vpc_peering_connection_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRoute<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#RouteArgs">RouteArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#Route">Route</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.Route.html">Route</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.RouteArgs.html">RouteArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination_<wbr>ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress_<wbr>only_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nat_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>peering_<wbr>connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Route Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Prefix<wbr>List<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Origin<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Prefix<wbr>List<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Origin<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination<wbr>Prefix<wbr>List<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">origin<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination_<wbr>ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination_<wbr>prefix_<wbr>list_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">egress_<wbr>only_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">nat_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-"
            title="">origin<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>peering_<wbr>connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Route Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#RouteState">RouteState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#Route">Route</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>destination_cidr_block=None<span class="p">, </span>destination_ipv6_cidr_block=None<span class="p">, </span>destination_prefix_list_id=None<span class="p">, </span>egress_only_gateway_id=None<span class="p">, </span>gateway_id=None<span class="p">, </span>instance_id=None<span class="p">, </span>instance_owner_id=None<span class="p">, </span>nat_gateway_id=None<span class="p">, </span>network_interface_id=None<span class="p">, </span>origin=None<span class="p">, </span>route_table_id=None<span class="p">, </span>state=None<span class="p">, </span>transit_gateway_id=None<span class="p">, </span>vpc_peering_connection_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRoute<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#RouteState">RouteState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#Route">Route</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.Route.html">Route</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.RouteState.html">RouteState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Route resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Prefix<wbr>List<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Prefix<wbr>List<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<wbr>Prefix<wbr>List<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<wbr>Only<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nat<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination_<wbr>ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination_<wbr>prefix_<wbr>list_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress_<wbr>only_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC Egress Only Internet Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC internet gateway or a virtual private gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nat_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC NAT gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 network interface.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the routing table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of an EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>peering_<wbr>connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of a VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







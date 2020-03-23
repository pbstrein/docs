
---
title: "VpcPeeringConnection"
block_external_search_index: true
---

Provides a resource to manage a VPC peering connection.

> **NOTE on VPC Peering Connections and VPC Peering Connection Options:** This provider provides
both a standalone VPC Peering Connection Options and a VPC Peering Connection
resource with `accepter` and `requester` attributes. Do not manage options for the same VPC peering
connection in both a VPC Peering Connection resource and a VPC Peering Connection Options resource.
Doing so will cause a conflict of options and will overwrite the options.
Using a VPC Peering Connection Options resource decouples management of the connection options from
management of the VPC Peering Connection and allows options to be set correctly in cross-account scenarios.

> **Note:** For cross-account (requester's AWS account differs from the accepter's AWS account) or inter-region
VPC Peering Connections use the `aws.ec2.VpcPeeringConnection` resource to manage the requester's side of the
connection and use the `aws.ec2.VpcPeeringConnectionAccepter` resource to manage the accepter's side of the connection.

## Notes

If both VPCs are not in the same AWS account do not enable the `auto_accept` attribute.
The accepter can manage its side of the connection using the `aws.ec2.VpcPeeringConnectionAccepter` resource
or accept the connection manually using the AWS Management Console, AWS CLI, through SDKs, etc.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/vpc_peering_connection.html.markdown.



## Create a VpcPeeringConnection Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpcPeeringConnection">VpcPeeringConnection</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpcPeeringConnectionArgs">VpcPeeringConnectionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">VpcPeeringConnection</span><span class="p">(resource_name, opts=None, </span>accepter=None<span class="p">, </span>auto_accept=None<span class="p">, </span>peer_owner_id=None<span class="p">, </span>peer_region=None<span class="p">, </span>peer_vpc_id=None<span class="p">, </span>requester=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVpcPeeringConnection<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnectionArgs">VpcPeeringConnectionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnection">VpcPeeringConnection</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnection.html">VpcPeeringConnection</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnectionArgs.html">VpcPeeringConnectionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">*Vpc<wbr>Peering<wbr>Connection<wbr>Accepter<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">*Vpc<wbr>Peering<wbr>Connection<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Dict[Vpc<wbr>Peering<wbr>Connection<wbr>Accepter]</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>accept<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">peer_<wbr>vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Dict[Vpc<wbr>Peering<wbr>Connection<wbr>Requester]</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## VpcPeeringConnection Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accept<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accept<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accept<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-"
            title="">peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-"
            title="">peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accept_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Dict[Vpc<wbr>Peering<wbr>Connection<wbr>Accepter]</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>accept<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-"
            title="">peer_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">peer_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-"
            title="">peer_<wbr>vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Dict[Vpc<wbr>Peering<wbr>Connection<wbr>Requester]</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing VpcPeeringConnection Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpcPeeringConnectionState">VpcPeeringConnectionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpcPeeringConnection">VpcPeeringConnection</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>accept_status=None<span class="p">, </span>accepter=None<span class="p">, </span>auto_accept=None<span class="p">, </span>peer_owner_id=None<span class="p">, </span>peer_region=None<span class="p">, </span>peer_vpc_id=None<span class="p">, </span>requester=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVpcPeeringConnection<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnectionState">VpcPeeringConnectionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnection">VpcPeeringConnection</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnection.html">VpcPeeringConnection</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnectionState.html">VpcPeeringConnectionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing VpcPeeringConnection resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Accept<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accept<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">*Vpc<wbr>Peering<wbr>Connection<wbr>Accepter<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">*Vpc<wbr>Peering<wbr>Connection<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accept<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Vpc<wbr>Peering<wbr>Connection<wbr>Accepter?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Accept<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer<wbr>Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Vpc<wbr>Peering<wbr>Connection<wbr>Requester?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accept_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the VPC Peering Connection request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionaccepter">Dict[Vpc<wbr>Peering<wbr>Connection<wbr>Accepter]</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>accept<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Accept the peering (both VPCs need to be in the same AWS account).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the owner of the peer VPC.
Defaults to the account ID the [AWS provider][1] is currently connected to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer_<wbr>region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region of the accepter VPC of the [VPC Peering Connection]. `auto_accept` must be `false`,
and use the `aws.ec2.VpcPeeringConnectionAccepter` to manage the accepter side.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">peer_<wbr>vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC with which you are creating the VPC Peering Connection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#vpcpeeringconnectionrequester">Dict[Vpc<wbr>Peering<wbr>Connection<wbr>Requester]</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### VpcPeeringConnectionAccepter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VpcPeeringConnectionAccepter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VpcPeeringConnectionAccepter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnectionAccepterTypeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnectionAccepterTypeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnectionAccepterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnectionAccepter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### VpcPeeringConnectionRequester
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#VpcPeeringConnectionRequester">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#VpcPeeringConnectionRequester">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnectionRequesterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcPeeringConnectionRequesterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnectionRequesterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcPeeringConnectionRequester.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC. This is
[not supported](https://docs.aws.amazon.com/vpc/latest/peering/modify-peering-connections.html) for
inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








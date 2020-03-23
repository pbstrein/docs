
---
title: "PeeringConnectionOptions"
block_external_search_index: true
---

Provides a resource to manage VPC peering connection options.

> **NOTE on VPC Peering Connections and VPC Peering Connection Options:** This provider provides
both a standalone VPC Peering Connection Options and a VPC Peering Connection
resource with `accepter` and `requester` attributes. Do not manage options for the same VPC peering
connection in both a VPC Peering Connection resource and a VPC Peering Connection Options resource.
Doing so will cause a conflict of options and will overwrite the options.
Using a VPC Peering Connection Options resource decouples management of the connection options from
management of the VPC Peering Connection and allows options to be set correctly in cross-region and
cross-account scenarios.

Basic usage:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const fooVpc = new aws.ec2.Vpc("foo", {
    cidrBlock: "10.0.0.0/16",
});
const bar = new aws.ec2.Vpc("bar", {
    cidrBlock: "10.1.0.0/16",
});
const fooVpcPeeringConnection = new aws.ec2.VpcPeeringConnection("foo", {
    autoAccept: true,
    peerVpcId: bar.id,
    vpcId: fooVpc.id,
});
const fooPeeringConnectionOptions = new aws.ec2.PeeringConnectionOptions("foo", {
    accepter: {
        allowRemoteVpcDnsResolution: true,
    },
    requester: {
        allowClassicLinkToRemoteVpc: true,
        allowVpcToRemoteClassicLink: true,
    },
    vpcPeeringConnectionId: fooVpcPeeringConnection.id,
});
```

Basic cross-account usage:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const requester = new aws.Provider("requester", {});
const accepter = new aws.Provider("accepter", {});
const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
    enableDnsHostnames: true,
    enableDnsSupport: true,
}, {provider: requester});
const peerVpc = new aws.ec2.Vpc("peer", {
    cidrBlock: "10.1.0.0/16",
    enableDnsHostnames: true,
    enableDnsSupport: true,
}, {provider: accepter});
const peerCallerIdentity = aws.getCallerIdentity({provider: accepter});
// Requester's side of the connection.
const peerVpcPeeringConnection = new aws.ec2.VpcPeeringConnection("peer", {
    autoAccept: false,
    peerOwnerId: peerCallerIdentity.accountId,
    peerVpcId: peerVpc.id,
    tags: {
        Side: "Requester",
    },
    vpcId: main.id,
}, {provider: requester});
// Accepter's side of the connection.
const peerVpcPeeringConnectionAccepter = new aws.ec2.VpcPeeringConnectionAccepter("peer", {
    autoAccept: true,
    tags: {
        Side: "Accepter",
    },
    vpcPeeringConnectionId: peerVpcPeeringConnection.id,
}, {provider: accepter});
const requesterPeeringConnectionOptions = new aws.ec2.PeeringConnectionOptions("requester", {
    requester: {
        allowRemoteVpcDnsResolution: true,
    },
    // As options can't be set until the connection has been accepted
    // create an explicit dependency on the accepter.
    vpcPeeringConnectionId: peerVpcPeeringConnectionAccepter.id,
}, {provider: requester});
const accepterPeeringConnectionOptions = new aws.ec2.PeeringConnectionOptions("accepter", {
    accepter: {
        allowRemoteVpcDnsResolution: true,
    },
    vpcPeeringConnectionId: peerVpcPeeringConnectionAccepter.id,
}, {provider: accepter});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/vpc_peering_connection_options.html.markdown.



## Create a PeeringConnectionOptions Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#PeeringConnectionOptions">PeeringConnectionOptions</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#PeeringConnectionOptionsArgs">PeeringConnectionOptionsArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">PeeringConnectionOptions</span><span class="p">(resource_name, opts=None, </span>accepter=None<span class="p">, </span>requester=None<span class="p">, </span>vpc_peering_connection_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPeeringConnectionOptions<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptionsArgs">PeeringConnectionOptionsArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptions">PeeringConnectionOptions</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptions.html">PeeringConnectionOptions</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptionsArgs.html">PeeringConnectionOptionsArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">*Peering<wbr>Connection<wbr>Options<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">*Peering<wbr>Connection<wbr>Options<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Dict[Peering<wbr>Connection<wbr>Options<wbr>Accepter]</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Dict[Peering<wbr>Connection<wbr>Options<wbr>Requester]</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>peering_<wbr>connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## PeeringConnectionOptions Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Dict[Peering<wbr>Connection<wbr>Options<wbr>Accepter]</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Dict[Peering<wbr>Connection<wbr>Options<wbr>Requester]</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>peering_<wbr>connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing PeeringConnectionOptions Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#PeeringConnectionOptionsState">PeeringConnectionOptionsState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#PeeringConnectionOptions">PeeringConnectionOptions</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>accepter=None<span class="p">, </span>requester=None<span class="p">, </span>vpc_peering_connection_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPeeringConnectionOptions<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptionsState">PeeringConnectionOptionsState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptions">PeeringConnectionOptions</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptions.html">PeeringConnectionOptions</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptionsState.html">PeeringConnectionOptionsState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing PeeringConnectionOptions resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">*Peering<wbr>Connection<wbr>Options<wbr>Accepter</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">*Peering<wbr>Connection<wbr>Options<wbr>Requester</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Peering<wbr>Connection<wbr>Options<wbr>Accepter?</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Peering<wbr>Connection<wbr>Options<wbr>Requester?</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Peering<wbr>Connection<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accepter<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsaccepter">Dict[Peering<wbr>Connection<wbr>Options<wbr>Accepter]</a></span>
    </dt>
    <dd>{{% md %}}An optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that accepts
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">requester<span class="property-indicator"></span>
        <span class="property-type"><a href="#peeringconnectionoptionsrequester">Dict[Peering<wbr>Connection<wbr>Options<wbr>Requester]</a></span>
    </dt>
    <dd>{{% md %}}A optional configuration block that allows for [VPC Peering Connection]
(http://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide) options to be set for the VPC that requests
the peering connection (a maximum of one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>peering_<wbr>connection_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the requester VPC peering connection.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### PeeringConnectionOptionsAccepter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PeeringConnectionOptionsAccepter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PeeringConnectionOptionsAccepter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptionsAccepterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptionsAccepterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptionsAccepterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptionsAccepter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
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
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
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
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
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
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PeeringConnectionOptionsRequester
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PeeringConnectionOptionsRequester">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PeeringConnectionOptionsRequester">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptionsRequesterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#PeeringConnectionOptionsRequesterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptionsRequesterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.PeeringConnectionOptionsRequester.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Classic<wbr>Link<wbr>To<wbr>Remote<wbr>Vpc<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local linked EC2-Classic instance to communicate
with instances in a peer VPC. This enables an outbound communication from the local ClassicLink connection
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
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
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
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
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
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
to the remote VPC. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Remote<wbr>Vpc<wbr>Dns<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to resolve public DNS hostnames to
private IP addresses when queried from instances in the peer VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allow<wbr>Vpc<wbr>To<wbr>Remote<wbr>Classic<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Allow a local VPC to communicate with a linked EC2-Classic
instance in a peer VPC. This enables an outbound communication from the local VPC to the remote ClassicLink
connection. This option is not supported for inter-region VPC peering.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








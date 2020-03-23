
---
title: "BgpPeer"
block_external_search_index: true
---

Provides a Direct Connect BGP peer resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const peer = new aws.directconnect.BgpPeer("peer", {
    addressFamily: "ipv6",
    bgpAsn: 65351,
    virtualInterfaceId: aws_dx_private_virtual_interface_foo.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/dx_bgp_peer.html.markdown.



## Create a BgpPeer Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#BgpPeer">BgpPeer</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#BgpPeerArgs">BgpPeerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BgpPeer</span><span class="p">(resource_name, opts=None, </span>address_family=None<span class="p">, </span>amazon_address=None<span class="p">, </span>bgp_asn=None<span class="p">, </span>bgp_auth_key=None<span class="p">, </span>customer_address=None<span class="p">, </span>virtual_interface_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBgpPeer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#BgpPeerArgs">BgpPeerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#BgpPeer">BgpPeer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.BgpPeer.html">BgpPeer</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.BgpPeerArgs.html">BgpPeerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
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

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
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

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
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

    <dt class="property-optional"
            title="Optional">customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
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

    <dt class="property-optional"
            title="Optional">customer_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## BgpPeer Output Properties

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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="">Bgp<wbr>Peer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bgp<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="">Bgp<wbr>Peer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bgp<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="">bgp<wbr>Peer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bgp<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws_<wbr>device<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="">bgp_<wbr>peer_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bgp_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">customer_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtual_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing BgpPeer Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#BgpPeerState">BgpPeerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#BgpPeer">BgpPeer</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>address_family=None<span class="p">, </span>amazon_address=None<span class="p">, </span>aws_device=None<span class="p">, </span>bgp_asn=None<span class="p">, </span>bgp_auth_key=None<span class="p">, </span>bgp_peer_id=None<span class="p">, </span>bgp_status=None<span class="p">, </span>customer_address=None<span class="p">, </span>virtual_interface_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBgpPeer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#BgpPeerState">BgpPeerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#BgpPeer">BgpPeer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.BgpPeer.html">BgpPeer</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.BgpPeerState.html">BgpPeerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing BgpPeer resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="Optional">Bgp<wbr>Peer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="Optional">Bgp<wbr>Peer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bgp<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="Optional">bgp<wbr>Peer<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
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
    <dd>{{% md %}}The IPv4 CIDR address to use to send traffic to Amazon.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws_<wbr>device<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Direct Connect endpoint on which the BGP peer terminates.
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
            title="Optional">bgp_<wbr>peer_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bgp_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Up/Down state of the BGP peer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">customer_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv4 CIDR destination address to which Amazon should send traffic.
Required for IPv4 BGP peers on public virtual interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Direct Connect virtual interface on which to create the BGP peer.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







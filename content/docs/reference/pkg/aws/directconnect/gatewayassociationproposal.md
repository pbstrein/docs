
---
title: "GatewayAssociationProposal"
block_external_search_index: true
---

Manages a Direct Connect Gateway Association Proposal, typically for enabling cross-account associations. For single account associations, see the [`aws.directconnect.GatewayAssociation` resource](https://www.terraform.io/docs/providers/aws/r/dx_gateway_association.html).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.directconnect.GatewayAssociationProposal("example", {
    associatedGatewayId: aws_vpn_gateway_example.id,
    dxGatewayId: aws_dx_gateway_example.id,
    dxGatewayOwnerAccountId: aws_dx_gateway_example.ownerAccountId,
});
```

A full example of how to create a VPN Gateway in one AWS account, create a Direct Connect Gateway in a second AWS account, and associate the VPN Gateway with the Direct Connect Gateway via the `aws.directconnect.GatewayAssociationProposal` and `aws.directconnect.GatewayAssociation` resources can be found in [the `./examples/dx-gateway-cross-account-vgw-association` directory within the Github Repository](https://github.com/providers/provider-aws/tree/master/examples/dx-gateway-cross-account-vgw-association).

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/dx_gateway_association_proposal.html.markdown.



## Create a GatewayAssociationProposal Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#GatewayAssociationProposal">GatewayAssociationProposal</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#GatewayAssociationProposalArgs">GatewayAssociationProposalArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">GatewayAssociationProposal</span><span class="p">(resource_name, opts=None, </span>allowed_prefixes=None<span class="p">, </span>associated_gateway_id=None<span class="p">, </span>dx_gateway_id=None<span class="p">, </span>dx_gateway_owner_account_id=None<span class="p">, </span>vpn_gateway_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewGatewayAssociationProposal<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#GatewayAssociationProposalArgs">GatewayAssociationProposalArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#GatewayAssociationProposal">GatewayAssociationProposal</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.GatewayAssociationProposal.html">GatewayAssociationProposal</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.GatewayAssociationProposalArgs.html">GatewayAssociationProposalArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed_<wbr>prefixes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dx_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">dx_<wbr>gateway_<wbr>owner_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}




## GatewayAssociationProposal Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associated<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associated<wbr>Gateway<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associated<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associated<wbr>Gateway<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associated<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associated<wbr>Gateway<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allowed_<wbr>prefixes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associated_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associated_<wbr>gateway_<wbr>owner_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associated_<wbr>gateway_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dx_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dx_<wbr>gateway_<wbr>owner_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpn_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}





## Look up an Existing GatewayAssociationProposal Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#GatewayAssociationProposalState">GatewayAssociationProposalState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/directconnect/#GatewayAssociationProposal">GatewayAssociationProposal</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allowed_prefixes=None<span class="p">, </span>associated_gateway_id=None<span class="p">, </span>associated_gateway_owner_account_id=None<span class="p">, </span>associated_gateway_type=None<span class="p">, </span>dx_gateway_id=None<span class="p">, </span>dx_gateway_owner_account_id=None<span class="p">, </span>vpn_gateway_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGatewayAssociationProposal<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#GatewayAssociationProposalState">GatewayAssociationProposalState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/directconnect?tab=doc#GatewayAssociationProposal">GatewayAssociationProposal</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.GatewayAssociationProposal.html">GatewayAssociationProposal</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Directconnect.GatewayAssociationProposalState.html">GatewayAssociationProposalState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing GatewayAssociationProposal resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associated<wbr>Gateway<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Prefixes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated<wbr>Gateway<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dx<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dx<wbr>Gateway<wbr>Owner<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed_<wbr>prefixes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}VPC prefixes (CIDRs) to advertise to the Direct Connect gateway. Defaults to the CIDR block of the VPC associated with the Virtual Gateway. To enable drift detection, must be configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated_<wbr>gateway_<wbr>owner_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VGW or transit gateway with which to associate the Direct Connect gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associated_<wbr>gateway_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the associated gateway, `transitGateway` or `virtualPrivateGateway`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dx_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Direct Connect Gateway identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dx_<wbr>gateway_<wbr>owner_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS Account identifier of the Direct Connect Gateway&#39;s owner.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpn_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}*Deprecated:* Use `associated_gateway_id` instead. Virtual Gateway identifier to associate with the Direct Connect Gateway.
{{% /md %}}<span class="property-deprecated">use &#39;associated_gateway_id&#39; argument instead</span></dd>

</dl>
{{% /choosable %}}







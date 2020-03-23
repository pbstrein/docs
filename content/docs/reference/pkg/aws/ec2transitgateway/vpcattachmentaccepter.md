
---
title: "VpcAttachmentAccepter"
block_external_search_index: true
---

Manages the accepter's side of an EC2 Transit Gateway VPC Attachment.

When a cross-account (requester's AWS account differs from the accepter's AWS account) EC2 Transit Gateway VPC Attachment
is created, an EC2 Transit Gateway VPC Attachment resource is automatically created in the accepter's account.
The requester can use the `aws.ec2transitgateway.VpcAttachment` resource to manage its side of the connection
and the accepter can use the `aws.ec2transitgateway.VpcAttachmentAccepter` resource to "adopt" its side of the
connection into management.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ec2transitgateway.VpcAttachmentAccepter("example", {
    tags: {
        Name: "Example cross-account attachment",
    },
    transitGatewayAttachmentId: aws_ec2_transit_gateway_vpc_attachment_example.id,
});
```

A full example of how to how to create a Transit Gateway in one AWS account, share it with a second AWS account, and attach a VPC in the second account to the Transit Gateway via the `aws.ec2transitgateway.VpcAttachment` and `aws.ec2transitgateway.VpcAttachmentAccepter` resources can be found in [the `./examples/transit-gateway-cross-account-vpc-attachment` directory within the Github Repository](https://github.com/providers/provider-aws/tree/master/examples/transit-gateway-cross-account-vpc-attachment).

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ec2_transit_gateway_vpc_attachment_accepter.html.markdown.



## Create a VpcAttachmentAccepter Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2transitgateway/#VpcAttachmentAccepter">VpcAttachmentAccepter</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2transitgateway/#VpcAttachmentAccepterArgs">VpcAttachmentAccepterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">VpcAttachmentAccepter</span><span class="p">(resource_name, opts=None, </span>tags=None<span class="p">, </span>transit_gateway_attachment_id=None<span class="p">, </span>transit_gateway_default_route_table_association=None<span class="p">, </span>transit_gateway_default_route_table_propagation=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVpcAttachmentAccepter<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2transitgateway?tab=doc#VpcAttachmentAccepterArgs">VpcAttachmentAccepterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2transitgateway?tab=doc#VpcAttachmentAccepter">VpcAttachmentAccepter</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2transitgateway.VpcAttachmentAccepter.html">VpcAttachmentAccepter</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2transitgateway.VpcAttachmentAccepterArgs.html">VpcAttachmentAccepterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">transit_<wbr>gateway_<wbr>attachment_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>default_<wbr>route_<wbr>table_<wbr>association<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>default_<wbr>route_<wbr>table_<wbr>propagation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## VpcAttachmentAccepter Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>attachment_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>default_<wbr>route_<wbr>table_<wbr>association<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>default_<wbr>route_<wbr>table_<wbr>propagation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing VpcAttachmentAccepter Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2transitgateway/#VpcAttachmentAccepterState">VpcAttachmentAccepterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2transitgateway/#VpcAttachmentAccepter">VpcAttachmentAccepter</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>dns_support=None<span class="p">, </span>ipv6_support=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>transit_gateway_attachment_id=None<span class="p">, </span>transit_gateway_default_route_table_association=None<span class="p">, </span>transit_gateway_default_route_table_propagation=None<span class="p">, </span>transit_gateway_id=None<span class="p">, </span>vpc_id=None<span class="p">, </span>vpc_owner_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVpcAttachmentAccepter<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2transitgateway?tab=doc#VpcAttachmentAccepterState">VpcAttachmentAccepterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2transitgateway?tab=doc#VpcAttachmentAccepter">VpcAttachmentAccepter</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2transitgateway.VpcAttachmentAccepter.html">VpcAttachmentAccepter</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2transitgateway.VpcAttachmentAccepterState.html">VpcAttachmentAccepterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing VpcAttachmentAccepter resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Support<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Support<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Support<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Attachment<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Association<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Default<wbr>Route<wbr>Table<wbr>Propagation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Gateway<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether DNS support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether IPv6 support is enabled. Valid values: `disable`, `enable`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value tags for the EC2 Transit Gateway VPC Attachment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>attachment_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the EC2 Transit Gateway Attachment to manage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>default_<wbr>route_<wbr>table_<wbr>association<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should be associated with the EC2 Transit Gateway association default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>default_<wbr>route_<wbr>table_<wbr>propagation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the VPC Attachment should propagate routes with the EC2 Transit Gateway propagation default route table. Default value: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>gateway_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 Transit Gateway.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of EC2 VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the AWS account that owns the EC2 VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







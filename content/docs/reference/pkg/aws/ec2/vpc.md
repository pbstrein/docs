
---
title: "Vpc"
block_external_search_index: true
---

Provides a VPC resource.

## Example Usage

Basic usage:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
```

Basic usage with tags:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
    instanceTenancy: "dedicated",
    tags: {
        Name: "main",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/vpc.html.markdown.



## Create a Vpc Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#Vpc">Vpc</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpcArgs">VpcArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Vpc</span><span class="p">(resource_name, opts=None, </span>assign_generated_ipv6_cidr_block=None<span class="p">, </span>cidr_block=None<span class="p">, </span>enable_classiclink=None<span class="p">, </span>enable_classiclink_dns_support=None<span class="p">, </span>enable_dns_hostnames=None<span class="p">, </span>enable_dns_support=None<span class="p">, </span>instance_tenancy=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVpc<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcArgs">VpcArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#Vpc">Vpc</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.Vpc.html">Vpc</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcArgs.html">VpcArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">assign_<wbr>generated_<wbr>ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>classiclink<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>classiclink_<wbr>dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>dns_<wbr>hostnames<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Vpc Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dhcp<wbr>Options<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Main<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dhcp<wbr>Options<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Main<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">dhcp<wbr>Options<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">main<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">assign_<wbr>generated_<wbr>ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-"
            title="">dhcp_<wbr>options_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>classiclink<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>classiclink_<wbr>dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>dns_<wbr>hostnames<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>association_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-"
            title="">main_<wbr>route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Vpc Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#VpcState">VpcState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#Vpc">Vpc</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>assign_generated_ipv6_cidr_block=None<span class="p">, </span>cidr_block=None<span class="p">, </span>default_network_acl_id=None<span class="p">, </span>default_route_table_id=None<span class="p">, </span>default_security_group_id=None<span class="p">, </span>dhcp_options_id=None<span class="p">, </span>enable_classiclink=None<span class="p">, </span>enable_classiclink_dns_support=None<span class="p">, </span>enable_dns_hostnames=None<span class="p">, </span>enable_dns_support=None<span class="p">, </span>instance_tenancy=None<span class="p">, </span>ipv6_association_id=None<span class="p">, </span>ipv6_cidr_block=None<span class="p">, </span>main_route_table_id=None<span class="p">, </span>owner_id=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVpc<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#VpcState">VpcState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#Vpc">Vpc</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.Vpc.html">Vpc</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.VpcState.html">VpcState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Vpc resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dhcp<wbr>Options<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Main<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dhcp<wbr>Options<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Main<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">assign<wbr>Generated<wbr>Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dhcp<wbr>Options<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Classiclink<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Classiclink<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Dns<wbr>Hostnames<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Dns<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">main<wbr>Route<wbr>Table<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">assign_<wbr>generated_<wbr>ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Requests an Amazon-provided IPv6 CIDR
block with a /56 prefix length for the VPC. You cannot specify the range of IP addresses, or
the size of the CIDR block. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block for the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the route table created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the security group created by default on VPC creation
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dhcp_<wbr>options_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>classiclink<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink
for the VPC. Only valid in regions and accounts that support EC2 Classic.
See the [ClassicLink documentation][1] for more information. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>classiclink_<wbr>dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable ClassicLink DNS Support for the VPC.
Only valid in regions and accounts that support EC2 Classic.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>dns_<wbr>hostnames<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS hostnames in the VPC. Defaults false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>dns_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag to enable/disable DNS support in the VPC. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A tenancy option for instances launched into the VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>association_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The association ID for the IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">main_<wbr>route_<wbr>table_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the main route table associated with
this VPC. Note that you can change a VPC&#39;s main route table by using an
[`aws.ec2.MainRouteTableAssociation`](https://www.terraform.io/docs/providers/aws/r/main_route_table_association.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







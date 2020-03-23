
---
title: "NetworkAcl"
block_external_search_index: true
---

Provides an network ACL resource. You might set up network ACLs with rules similar
to your security groups in order to add an additional layer of security to your VPC.

> **NOTE on Network ACLs and Network ACL Rules:** This provider currently
provides both a standalone Network ACL Rule resource and a Network ACL resource with rules
defined in-line. At this time you cannot use a Network ACL with in-line rules
in conjunction with any Network ACL Rule resources. Doing so will cause
a conflict of rule settings and will overwrite rules.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.NetworkAcl("main", {
    egress: [{
        action: "allow",
        cidrBlock: "10.3.0.0/18",
        fromPort: 443,
        protocol: "tcp",
        ruleNo: 200,
        toPort: 443,
    }],
    ingress: [{
        action: "allow",
        cidrBlock: "10.3.0.0/18",
        fromPort: 80,
        protocol: "tcp",
        ruleNo: 100,
        toPort: 80,
    }],
    tags: {
        Name: "main",
    },
    vpcId: aws_vpc_main.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/network_acl.html.markdown.



## Create a NetworkAcl Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAcl">NetworkAcl</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAclArgs">NetworkAclArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NetworkAcl</span><span class="p">(resource_name, opts=None, </span>egress=None<span class="p">, </span>ingress=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNetworkAcl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclArgs">NetworkAclArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAcl">NetworkAcl</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAcl.html">NetworkAcl</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclArgs.html">NetworkAclArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">List&lt;Network<wbr>Acl<wbr>Egress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">List&lt;Network<wbr>Acl<wbr>Ingress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">[]Network<wbr>Acl<wbr>Egress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">[]Network<wbr>Acl<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">Network<wbr>Acl<wbr>Egress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">Network<wbr>Acl<wbr>Ingress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">List[Network<wbr>Acl<wbr>Egress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">List[Network<wbr>Acl<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## NetworkAcl Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">List&lt;Network<wbr>Acl<wbr>Egress&gt;</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">List&lt;Network<wbr>Acl<wbr>Ingress&gt;</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">[]Network<wbr>Acl<wbr>Egress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">[]Network<wbr>Acl<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">Network<wbr>Acl<wbr>Egress[]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">Network<wbr>Acl<wbr>Ingress[]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">List[Network<wbr>Acl<wbr>Egress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">List[Network<wbr>Acl<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing NetworkAcl Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAclState">NetworkAclState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAcl">NetworkAcl</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>egress=None<span class="p">, </span>ingress=None<span class="p">, </span>owner_id=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNetworkAcl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclState">NetworkAclState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAcl">NetworkAcl</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAcl.html">NetworkAcl</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclState.html">NetworkAclState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing NetworkAcl resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">List&lt;Network<wbr>Acl<wbr>Egress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">List&lt;Network<wbr>Acl<wbr>Ingress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">[]Network<wbr>Acl<wbr>Egress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">[]Network<wbr>Acl<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">Network<wbr>Acl<wbr>Egress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">Network<wbr>Acl<wbr>Ingress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclegress">List[Network<wbr>Acl<wbr>Egress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#networkaclingress">List[Network<wbr>Acl<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
This argument is processed in [attribute-as-blocks mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to
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
    <dd>{{% md %}}The ID of the associated VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### NetworkAclEgress
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#NetworkAclEgress">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NetworkAclEgress">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclEgressArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclEgressOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclEgressArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclEgress.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### NetworkAclIngress
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#NetworkAclIngress">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NetworkAclIngress">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclIngressArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclIngressOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclIngressArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclIngress.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CIDR block to match. This must be a
valid network mask.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The ICMP type code to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The ICMP type to be used. Default 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to match. If using the -1 &#39;all&#39;
protocol, you must specify a from and to port of 0.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>No<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The rule number. Used for ordering.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








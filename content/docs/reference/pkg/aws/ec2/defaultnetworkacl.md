
---
title: "DefaultNetworkAcl"
block_external_search_index: true
---

Provides a resource to manage the default AWS Network ACL. VPC Only.

Each VPC created in AWS comes with a Default Network ACL that can be managed, but not
destroyed. **This is an advanced resource**, and has special caveats to be aware
of when using it. Please read this document in its entirety before using this
resource.

The `aws.ec2.DefaultNetworkAcl` behaves differently from normal resources, in that
this provider does not _create_ this resource, but instead attempts to "adopt" it
into management. We can do this because each VPC created has a Default Network
ACL that cannot be destroyed, and is created with a known set of default rules.

When this provider first adopts the Default Network ACL, it **immediately removes all
rules in the ACL**. It then proceeds to create any rules specified in the
configuration. This step is required so that only the rules specified in the
configuration are created.

This resource treats its inline rules as absolute; only the rules defined
inline are created, and any additions/removals external to this resource will
result in diffs being shown. For these reasons, this resource is incompatible with the
`aws.ec2.NetworkAclRule` resource.

For more information about Network ACLs, see the AWS Documentation on
[Network ACLs][aws-network-acls].

## Example config to deny all traffic to any Subnet in the Default Network ACL

This config denies all traffic in the Default ACL. This can be useful if you
want a locked down default to force all resources in the VPC to assign a
non-default ACL.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const mainvpc = new aws.ec2.Vpc("mainvpc", {
    cidrBlock: "10.1.0.0/16",
});
const defaultDefaultNetworkAcl = new aws.ec2.DefaultNetworkAcl("default", {
    defaultNetworkAclId: mainvpc.defaultNetworkAclId,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/default_network_acl.html.markdown.



## Create a DefaultNetworkAcl Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#DefaultNetworkAcl">DefaultNetworkAcl</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#DefaultNetworkAclArgs">DefaultNetworkAclArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DefaultNetworkAcl</span><span class="p">(resource_name, opts=None, </span>default_network_acl_id=None<span class="p">, </span>egress=None<span class="p">, </span>ingress=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDefaultNetworkAcl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAclArgs">DefaultNetworkAclArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAcl">DefaultNetworkAcl</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAcl.html">DefaultNetworkAcl</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAclArgs.html">DefaultNetworkAclArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">List&lt;Default<wbr>Network<wbr>Acl<wbr>Egress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">List&lt;Default<wbr>Network<wbr>Acl<wbr>Ingress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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

    <dt class="property-required"
            title="Required">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">[]Default<wbr>Network<wbr>Acl<wbr>Egress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">[]Default<wbr>Network<wbr>Acl<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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

    <dt class="property-required"
            title="Required">default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">Default<wbr>Network<wbr>Acl<wbr>Egress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">Default<wbr>Network<wbr>Acl<wbr>Ingress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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

    <dt class="property-required"
            title="Required">default_<wbr>network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">List[Default<wbr>Network<wbr>Acl<wbr>Egress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">List[Default<wbr>Network<wbr>Acl<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## DefaultNetworkAcl Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">List&lt;Default<wbr>Network<wbr>Acl<wbr>Egress&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">List&lt;Default<wbr>Network<wbr>Acl<wbr>Ingress&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">[]Default<wbr>Network<wbr>Acl<wbr>Egress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">[]Default<wbr>Network<wbr>Acl<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">Default<wbr>Network<wbr>Acl<wbr>Egress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">Default<wbr>Network<wbr>Acl<wbr>Ingress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">default_<wbr>network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-"
            title="">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">List[Default<wbr>Network<wbr>Acl<wbr>Egress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">List[Default<wbr>Network<wbr>Acl<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing DefaultNetworkAcl Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#DefaultNetworkAclState">DefaultNetworkAclState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#DefaultNetworkAcl">DefaultNetworkAcl</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>default_network_acl_id=None<span class="p">, </span>egress=None<span class="p">, </span>ingress=None<span class="p">, </span>owner_id=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDefaultNetworkAcl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAclState">DefaultNetworkAclState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAcl">DefaultNetworkAcl</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAcl.html">DefaultNetworkAcl</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAclState.html">DefaultNetworkAclState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing DefaultNetworkAcl resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">List&lt;Default<wbr>Network<wbr>Acl<wbr>Egress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">List&lt;Default<wbr>Network<wbr>Acl<wbr>Ingress<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">[]Default<wbr>Network<wbr>Acl<wbr>Egress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">[]Default<wbr>Network<wbr>Acl<wbr>Ingress</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default<wbr>Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">Default<wbr>Network<wbr>Acl<wbr>Egress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">Default<wbr>Network<wbr>Acl<wbr>Ingress[]?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default_<wbr>network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Network ACL ID to manage. This
attribute is exported from `aws.ec2.Vpc`, or manually found via the AWS Console.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclegress">List[Default<wbr>Network<wbr>Acl<wbr>Egress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an egress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ingress<span class="property-indicator"></span>
        <span class="property-type"><a href="#defaultnetworkaclingress">List[Default<wbr>Network<wbr>Acl<wbr>Ingress]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an ingress rule. Parameters defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AWS account that owns the Default Network ACL
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Subnet IDs to apply the ACL to. See the
notes below on managing Subnets in the Default Network ACL
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
    <dd>{{% md %}}The ID of the associated VPC
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DefaultNetworkAclEgress
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DefaultNetworkAclEgress">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DefaultNetworkAclEgress">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAclEgressArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAclEgressOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAclEgressArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAclEgress.html">output</a> API doc for this type.
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





#### DefaultNetworkAclIngress
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DefaultNetworkAclIngress">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DefaultNetworkAclIngress">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAclIngressArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#DefaultNetworkAclIngressOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAclIngressArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.DefaultNetworkAclIngress.html">output</a> API doc for this type.
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








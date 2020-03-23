
---
title: "NetworkAclRule"
block_external_search_index: true
---

Creates an entry (a rule) in a network ACL with the specified rule number.

> **NOTE on Network ACLs and Network ACL Rules:** This provider currently
provides both a standalone Network ACL Rule resource and a Network ACL resource with rules
defined in-line. At this time you cannot use a Network ACL with in-line rules
in conjunction with any Network ACL Rule resources. Doing so will cause
a conflict of rule settings and will overwrite rules.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/network_acl_rule.html.markdown.



## Create a NetworkAclRule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAclRule">NetworkAclRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAclRuleArgs">NetworkAclRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NetworkAclRule</span><span class="p">(resource_name, opts=None, </span>cidr_block=None<span class="p">, </span>egress=None<span class="p">, </span>from_port=None<span class="p">, </span>icmp_code=None<span class="p">, </span>icmp_type=None<span class="p">, </span>ipv6_cidr_block=None<span class="p">, </span>network_acl_id=None<span class="p">, </span>protocol=None<span class="p">, </span>rule_action=None<span class="p">, </span>rule_number=None<span class="p">, </span>to_port=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNetworkAclRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclRuleArgs">NetworkAclRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclRule">NetworkAclRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclRule.html">NetworkAclRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclRuleArgs.html">NetworkAclRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## NetworkAclRule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Egress<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Egress<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-"
            title="">egress<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-"
            title="">icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-"
            title="">egress<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-"
            title="">icmp_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">icmp_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing NetworkAclRule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAclRuleState">NetworkAclRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#NetworkAclRule">NetworkAclRule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>cidr_block=None<span class="p">, </span>egress=None<span class="p">, </span>from_port=None<span class="p">, </span>icmp_code=None<span class="p">, </span>icmp_type=None<span class="p">, </span>ipv6_cidr_block=None<span class="p">, </span>network_acl_id=None<span class="p">, </span>protocol=None<span class="p">, </span>rule_action=None<span class="p">, </span>rule_number=None<span class="p">, </span>to_port=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNetworkAclRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclRuleState">NetworkAclRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#NetworkAclRule">NetworkAclRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclRule.html">NetworkAclRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.NetworkAclRuleState.html">NetworkAclRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing NetworkAclRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Egress<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The network range to allow or deny, in CIDR notation (for example 172.16.0.0/24 ).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">egress<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this is an egress rule (rule is applied to traffic leaving the subnet). Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The from port to match.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP code. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">icmp_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ICMP protocol: The ICMP type. Required if specifying ICMP for the protocol. e.g. -1
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IPv6 CIDR block to allow or deny.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the network ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. A value of -1 means all protocols.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether to allow or deny the traffic that matches the rule. Accepted values: `allow` | `deny`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The rule number for the entry (for example, 100). ACL entries are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The to port to match.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







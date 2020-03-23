
---
title: "SecurityGroupRule"
block_external_search_index: true
---

Provides a security group rule resource. Represents a single `ingress` or
`egress` group rule, which can be added to external Security Groups.

> **NOTE on Security Groups and Security Group Rules:** This provider currently
provides both a standalone Security Group Rule resource (a single `ingress` or
`egress` rule), and a Security Group resource with `ingress` and `egress` rules
defined in-line. At this time you cannot use a Security Group with in-line rules
in conjunction with any Security Group Rule resources. Doing so will cause
a conflict of rule settings and will overwrite rules.

> **NOTE:** Setting `protocol = "all"` or `protocol = -1` with `from_port` and `to_port` will result in the EC2 API creating a security group rule with all ports open. This API behavior cannot be controlled by this provider and may generate warnings in the future.

> **NOTE:** Referencing Security Groups across VPC peering has certain restrictions. More information is available in the [VPC Peering User Guide](https://docs.aws.amazon.com/vpc/latest/peering/vpc-peering-security-groups.html).

## Usage with prefix list IDs

Prefix list IDs are manged by AWS internally. Prefix list IDs
are associated with a prefix list name, or service name, that is linked to a specific region.
Prefix list IDs are exported on VPC Endpoints, so you can use this format:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

// ...
const myEndpoint = new aws.ec2.VpcEndpoint("my_endpoint", {});
const allowAll = new aws.ec2.SecurityGroupRule("allow_all", {
    fromPort: 0,
    prefixListIds: [myEndpoint.prefixListId],
    protocol: "-1",
    securityGroupId: "sg-123456",
    toPort: 0,
    type: "egress",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/security_group_rule.html.markdown.



## Create a SecurityGroupRule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SecurityGroupRule">SecurityGroupRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SecurityGroupRuleArgs">SecurityGroupRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SecurityGroupRule</span><span class="p">(resource_name, opts=None, </span>cidr_blocks=None<span class="p">, </span>description=None<span class="p">, </span>from_port=None<span class="p">, </span>ipv6_cidr_blocks=None<span class="p">, </span>prefix_list_ids=None<span class="p">, </span>protocol=None<span class="p">, </span>security_group_id=None<span class="p">, </span>self=None<span class="p">, </span>source_security_group_id=None<span class="p">, </span>to_port=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSecurityGroupRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SecurityGroupRuleArgs">SecurityGroupRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SecurityGroupRule">SecurityGroupRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SecurityGroupRule.html">SecurityGroupRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SecurityGroupRuleArgs.html">SecurityGroupRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr_<wbr>blocks<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>blocks<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix_<wbr>list_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SecurityGroupRule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Self<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Self<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">self<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">cidr_<wbr>blocks<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>cidr_<wbr>blocks<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">prefix_<wbr>list_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">self<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SecurityGroupRule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SecurityGroupRuleState">SecurityGroupRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SecurityGroupRule">SecurityGroupRule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>cidr_blocks=None<span class="p">, </span>description=None<span class="p">, </span>from_port=None<span class="p">, </span>ipv6_cidr_blocks=None<span class="p">, </span>prefix_list_ids=None<span class="p">, </span>protocol=None<span class="p">, </span>security_group_id=None<span class="p">, </span>self=None<span class="p">, </span>source_security_group_id=None<span class="p">, </span>to_port=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSecurityGroupRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SecurityGroupRuleState">SecurityGroupRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SecurityGroupRule">SecurityGroupRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SecurityGroupRule.html">SecurityGroupRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SecurityGroupRuleState.html">SecurityGroupRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SecurityGroupRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Cidr<wbr>Blocks<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<wbr>List<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cidr_<wbr>blocks<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of CIDR blocks. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The start port (or ICMP type number if protocol is &#34;icmp&#34; or &#34;icmpv6&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>cidr_<wbr>blocks<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of IPv6 CIDR blocks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix_<wbr>list_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of prefix list IDs (for allowing access to VPC endpoints).
Only valid with `egress`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. If not icmp, icmpv6, tcp, udp, or all use the [protocol number](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security group to apply this rule to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the security group itself will be added as
a source to this ingress rule. Cannot be specified with `source_security_group_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The security group id to allow access to/from,
depending on the `type`. Cannot be specified with `cidr_blocks` and `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The end port (or ICMP code if protocol is &#34;icmp&#34;).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of rule being created. Valid options are `ingress` (inbound)
or `egress` (outbound).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







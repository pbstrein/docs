
---
title: "TrafficMirrorFilterRule"
block_external_search_index: true
---




## Create a TrafficMirrorFilterRule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#TrafficMirrorFilterRule">TrafficMirrorFilterRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#TrafficMirrorFilterRuleArgs">TrafficMirrorFilterRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">TrafficMirrorFilterRule</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>destination_cidr_block=None<span class="p">, </span>destination_port_range=None<span class="p">, </span>protocol=None<span class="p">, </span>rule_action=None<span class="p">, </span>rule_number=None<span class="p">, </span>source_cidr_block=None<span class="p">, </span>source_port_range=None<span class="p">, </span>traffic_direction=None<span class="p">, </span>traffic_mirror_filter_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTrafficMirrorFilterRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRuleArgs">TrafficMirrorFilterRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRule">TrafficMirrorFilterRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRule.html">TrafficMirrorFilterRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRuleArgs.html">TrafficMirrorFilterRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">*Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">*Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination_<wbr>port_<wbr>range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Dict[Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>port_<wbr>range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Dict[Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">traffic_<wbr>direction<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">traffic_<wbr>mirror_<wbr>filter_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## TrafficMirrorFilterRule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">*Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">*Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination_<wbr>port_<wbr>range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Dict[Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>port_<wbr>range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Dict[Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic_<wbr>direction<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-"
            title="">traffic_<wbr>mirror_<wbr>filter_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing TrafficMirrorFilterRule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#TrafficMirrorFilterRuleState">TrafficMirrorFilterRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#TrafficMirrorFilterRule">TrafficMirrorFilterRule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>destination_cidr_block=None<span class="p">, </span>destination_port_range=None<span class="p">, </span>protocol=None<span class="p">, </span>rule_action=None<span class="p">, </span>rule_number=None<span class="p">, </span>source_cidr_block=None<span class="p">, </span>source_port_range=None<span class="p">, </span>traffic_direction=None<span class="p">, </span>traffic_mirror_filter_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTrafficMirrorFilterRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRuleState">TrafficMirrorFilterRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRule">TrafficMirrorFilterRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRule.html">TrafficMirrorFilterRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRuleState.html">TrafficMirrorFilterRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing TrafficMirrorFilterRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">*Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">*Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Cidr<wbr>Block<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Port<wbr>Range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range?</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Direction<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic<wbr>Mirror<wbr>Filter<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description of the traffic mirror filter rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination_<wbr>port_<wbr>range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterruledestinationportrange">Dict[Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Destination<wbr>Port<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}The destination port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The protocol number, for example 17 (UDP), to assign to the Traffic Mirror rule. For information about the protocol value, see [Protocol Numbers](https://www.iana.org/assignments/protocol-numbers/protocol-numbers.xhtml) on the Internet Assigned Numbers Authority (IANA) website.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The action to take (accept | reject) on the filtered traffic. Valid values are `accept` and `reject`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of the Traffic Mirror rule. This number must be unique for each Traffic Mirror rule in a given direction. The rules are processed in ascending order by rule number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>cidr_<wbr>block<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The source CIDR block to assign to the Traffic Mirror rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>port_<wbr>range<span class="property-indicator"></span>
        <span class="property-type"><a href="#trafficmirrorfilterrulesourceportrange">Dict[Traffic<wbr>Mirror<wbr>Filter<wbr>Rule<wbr>Source<wbr>Port<wbr>Range]</a></span>
    </dt>
    <dd>{{% md %}}The source port range. Supported only when the protocol is set to TCP(6) or UDP(17). See Traffic mirror port range documented below
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>direction<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The direction of traffic to be captured. Valid values are `ingress` and `egress`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">traffic_<wbr>mirror_<wbr>filter_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the traffic mirror filter to which this rule should be added
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### TrafficMirrorFilterRuleDestinationPortRange
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TrafficMirrorFilterRuleDestinationPortRange">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TrafficMirrorFilterRuleDestinationPortRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRuleDestinationPortRangeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRuleDestinationPortRangeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRuleDestinationPortRangeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRuleDestinationPortRange.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TrafficMirrorFilterRuleSourcePortRange
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TrafficMirrorFilterRuleSourcePortRange">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TrafficMirrorFilterRuleSourcePortRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRuleSourcePortRangeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#TrafficMirrorFilterRuleSourcePortRangeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRuleSourcePortRangeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.TrafficMirrorFilterRuleSourcePortRange.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">From<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">To<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">from<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">from_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Starting port of the range
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">to_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Ending port of the range
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








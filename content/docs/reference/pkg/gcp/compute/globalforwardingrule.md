
---
title: "GlobalForwardingRule"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a GlobalForwardingRule Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#GlobalForwardingRule">GlobalForwardingRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#GlobalForwardingRuleArgs">GlobalForwardingRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">GlobalForwardingRule</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>ip_address=None<span class="p">, </span>ip_protocol=None<span class="p">, </span>ip_version=None<span class="p">, </span>labels=None<span class="p">, </span>load_balancing_scheme=None<span class="p">, </span>metadata_filters=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>port_range=None<span class="p">, </span>project=None<span class="p">, </span>target=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewGlobalForwardingRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRuleArgs">GlobalForwardingRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRule">GlobalForwardingRule</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRule.html">GlobalForwardingRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRuleArgs.html">GlobalForwardingRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a GlobalForwardingRule resource with the given unique name, arguments, and options.

{{% lang nodejs %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang go %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang csharp %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

The following arguments are supported:


{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">List&lt;Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">[]Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load_<wbr>balancing_<wbr>scheme</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata_<wbr>filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">List[Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## GlobalForwardingRule Output Properties

The following output properties are available:



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">List&lt;Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">[]Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load_<wbr>balancing_<wbr>scheme</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata_<wbr>filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">List[Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing GlobalForwardingRule Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#GlobalForwardingRuleState">GlobalForwardingRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#GlobalForwardingRule">GlobalForwardingRule</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>ip_address=None<span class="p">, </span>ip_protocol=None<span class="p">, </span>ip_version=None<span class="p">, </span>label_fingerprint=None<span class="p">, </span>labels=None<span class="p">, </span>load_balancing_scheme=None<span class="p">, </span>metadata_filters=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>port_range=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, </span>target=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGlobalForwardingRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRuleState">GlobalForwardingRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRule">GlobalForwardingRule</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRule.html">GlobalForwardingRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRuleState.html">GlobalForwardingRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing GlobalForwardingRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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


{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">List&lt;Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">[]Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata<wbr>Filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address that this forwarding rule is serving on behalf of. Addresses are restricted based on the forwarding
rule&#39;s load balancing scheme (EXTERNAL or INTERNAL) and scope (global or regional). When the load balancing scheme is
EXTERNAL, for global forwarding rules, the address must be a global IP, and for regional forwarding rules, the address
must live in the same region as the forwarding rule. If this field is empty, an ephemeral IPv4 address from the same
scope (global or regional) will be assigned. A regional forwarding rule supports IPv4 only. A global forwarding rule
supports either IPv4 or IPv6. When the load balancing scheme is INTERNAL, this can only be an RFC 1918 IP address
belonging to the network/subnet configured for the forwarding rule. By default, if this field is empty, an ephemeral
internal IP address will be automatically allocated from the IP range of the subnet or network configured for this
forwarding rule. An address must be specified by a literal IP address. ~&gt; **NOTE**: While the API allows you to specify
various resource paths for an address resource instead, Terraform requires this to specifically be an IP address to
avoid needing to fetching the IP address from resource paths on refresh or unnecessary diffs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP protocol to which this rule applies. Valid options are TCP, UDP, ESP, AH, SCTP or ICMP. When the load balancing
scheme is INTERNAL_SELF_MANAGED, only TCP is valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP Version that will be used by this global forwarding rule. Valid options are IPV4 or IPV6.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint used for optimistic locking of this resource. Used internally during updates.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Labels to apply to this forwarding rule. A list of key-&gt;value pairs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load_<wbr>balancing_<wbr>scheme</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This signifies what the GlobalForwardingRule will be used for. The value of INTERNAL_SELF_MANAGED means that this will
be used for Internal Global HTTP(S) LB. The value of EXTERNAL means that this will be used for External Global Load
Balancing (HTTP(S) LB, External TCP/UDP LB, SSL Proxy) NOTE: Currently global forwarding rules cannot be used for
INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata_<wbr>filters</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilter">List[Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Opaque filter criteria used by Loadbalancer to restrict routing configuration to a limited set xDS compliant clients. In
their xDS requests to Loadbalancer, xDS clients present node metadata. If a match takes place, the relevant routing
configuration is made available to those proxies. For each metadataFilter in this list, if its filterMatchCriteria is
set to MATCH_ANY, at least one of the filterLabels must match the corresponding label provided in the metadata. If its
filterMatchCriteria is set to MATCH_ALL, then all of its filterLabels must match with corresponding labels in the
provided metadata. metadataFilters specified here can be overridden by those specified in the UrlMap that this
ForwardingRule references. metadataFilters only applies to Loadbalancers that have their loadBalancingScheme set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the resource; provided by the client when the resource is created. The name must be 1-63 characters long, and
comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
&#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must be a lowercase letter, and all following characters
must be a dash, lowercase letter, or digit, except the last character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is not used for external load balancing. For INTERNAL_SELF_MANAGED load balancing, this field identifies the
network that the load balanced IP should belong to for this global forwarding rule. If this field is not specified, the
default network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the target field for TargetHttpProxy, TargetHttpsProxy, TargetSslProxy, TargetTcpProxy,
TargetVpnGateway, TargetPool, TargetInstance. Applicable only when IPProtocol is TCP, UDP, or SCTP, only packets
addressed to ports in the specified range will be forwarded to target. Forwarding rules with the same [IPAddress,
IPProtocol] pair must have disjoint port ranges. Some types of forwarding target have constraints on the acceptable
ports: * TargetHttpProxy: 80, 8080 * TargetHttpsProxy: 443 * TargetTcpProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700,
993, 995, 1883, 5222 * TargetSslProxy: 25, 43, 110, 143, 195, 443, 465, 587, 700, 993, 995, 1883, 5222 *
TargetVpnGateway: 500, 4500
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the target resource to receive the matched traffic. The forwarded traffic must be of a type appropriate to
the target object. For INTERNAL_SELF_MANAGED load balancing, only HTTP and HTTPS targets are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### GlobalForwardingRuleMetadataFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GlobalForwardingRuleMetadataFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GlobalForwardingRuleMetadataFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRuleMetadataFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRuleMetadataFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRuleMetadataFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRuleMetadataFilter.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Filter<wbr>Labels</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilterfilterlabel">List&lt;Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter<wbr>Filter<wbr>Label<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter<wbr>Match<wbr>Criteria</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Filter<wbr>Labels</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilterfilterlabel">[]Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter<wbr>Filter<wbr>Label</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter<wbr>Match<wbr>Criteria</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">filter<wbr>Labels</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilterfilterlabel">Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter<wbr>Filter<wbr>Label[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter<wbr>Match<wbr>Criteria</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">filter<wbr>Labels</td>
            <td class="align-top">
                
                <code><a href="#globalforwardingrulemetadatafilterfilterlabel">List[Global<wbr>Forwarding<wbr>Rule<wbr>Metadata<wbr>Filter<wbr>Filter<wbr>Label]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter<wbr>Match<wbr>Criteria</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GlobalForwardingRuleMetadataFilterFilterLabel
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GlobalForwardingRuleMetadataFilterFilterLabel">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GlobalForwardingRuleMetadataFilterFilterLabel">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRuleMetadataFilterFilterLabelArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GlobalForwardingRuleMetadataFilterFilterLabelOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRuleMetadataFilterFilterLabelArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GlobalForwardingRuleMetadataFilterFilterLabel.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








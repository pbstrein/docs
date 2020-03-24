
---
title: "ForwardingRule"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A ForwardingRule resource. A ForwardingRule resource specifies which pool
of target virtual machines to forward a packet to if it matches the given
[IPAddress, IPProtocol, portRange] tuple.


To get more information about ForwardingRule, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/v1/forwardingRules)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/compute/docs/load-balancing/network/forwarding-rules)

## Example Usage - Forwarding Rule Global Internallb


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const hc = new gcp.compute.HealthCheck("hc", {
    checkIntervalSec: 1,
    tcpHealthCheck: {
        port: 80,
    },
    timeoutSec: 1,
});
const backend = new gcp.compute.RegionBackendService("backend", {
    healthChecks: hc.selfLink,
    region: "us-central1",
});
const defaultNetwork = new gcp.compute.Network("default", {
    autoCreateSubnetworks: false,
});
const defaultSubnetwork = new gcp.compute.Subnetwork("default", {
    ipCidrRange: "10.0.0.0/16",
    network: defaultNetwork.selfLink,
    region: "us-central1",
});
// Forwarding rule for Internal Load Balancing
const defaultForwardingRule = new gcp.compute.ForwardingRule("default", {
    allPorts: true,
    allowGlobalAccess: true,
    backendService: backend.selfLink,
    loadBalancingScheme: "INTERNAL",
    network: defaultNetwork.name,
    region: "us-central1",
    subnetwork: defaultSubnetwork.name,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_forwarding_rule.html.markdown.



## Create a ForwardingRule Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#ForwardingRule">ForwardingRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#ForwardingRuleArgs">ForwardingRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ForwardingRule</span><span class="p">(resource_name, opts=None, </span>all_ports=None<span class="p">, </span>allow_global_access=None<span class="p">, </span>backend_service=None<span class="p">, </span>description=None<span class="p">, </span>ip_address=None<span class="p">, </span>ip_protocol=None<span class="p">, </span>is_mirroring_collector=None<span class="p">, </span>labels=None<span class="p">, </span>load_balancing_scheme=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>network_tier=None<span class="p">, </span>port_range=None<span class="p">, </span>ports=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>service_label=None<span class="p">, </span>subnetwork=None<span class="p">, </span>target=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewForwardingRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#ForwardingRuleArgs">ForwardingRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#ForwardingRule">ForwardingRule</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.ForwardingRule.html">ForwardingRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.ForwardingRuleArgs.html">ForwardingRuleArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ForwardingRule resource with the given unique name, arguments, and options.

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
            <td class="align-top">All<wbr>Ports</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">All<wbr>Ports</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Label</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">all<wbr>Ports</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">all_<wbr>ports</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow_<wbr>global_<wbr>access</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is_<wbr>mirroring_<wbr>collector</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>label</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ForwardingRule Output Properties

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
            <td class="align-top">All<wbr>Ports</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
            <td class="align-top">{{% md %}} This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
            <td class="align-top">{{% md %}} For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">Service<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">All<wbr>Ports</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
            <td class="align-top">{{% md %}} This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
            <td class="align-top">{{% md %}} For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">Service<wbr>Label</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">all<wbr>Ports</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
            <td class="align-top">{{% md %}} This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
            <td class="align-top">{{% md %}} For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">service<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">all_<wbr>ports</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow_<wbr>global_<wbr>access</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is_<wbr>mirroring_<wbr>collector</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
            <td class="align-top">{{% md %}} This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
            <td class="align-top">{{% md %}} For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">service_<wbr>label</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ForwardingRule Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#ForwardingRuleState">ForwardingRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#ForwardingRule">ForwardingRule</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>all_ports=None<span class="p">, </span>allow_global_access=None<span class="p">, </span>backend_service=None<span class="p">, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>ip_address=None<span class="p">, </span>ip_protocol=None<span class="p">, </span>is_mirroring_collector=None<span class="p">, </span>label_fingerprint=None<span class="p">, </span>labels=None<span class="p">, </span>load_balancing_scheme=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>network_tier=None<span class="p">, </span>port_range=None<span class="p">, </span>ports=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>self_link=None<span class="p">, </span>service_label=None<span class="p">, </span>service_name=None<span class="p">, </span>subnetwork=None<span class="p">, </span>target=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetForwardingRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#ForwardingRuleState">ForwardingRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#ForwardingRule">ForwardingRule</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.ForwardingRule.html">ForwardingRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.ForwardingRuleState.html">ForwardingRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ForwardingRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">All<wbr>Ports</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">Service<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">All<wbr>Ports</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">Ports</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">Service<wbr>Label</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">all<wbr>Ports</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow<wbr>Global<wbr>Access</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Mirroring<wbr>Collector</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">service<wbr>Label</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
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
            <td class="align-top">all_<wbr>ports</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For internal TCP/UDP load balancing (i.e. load balancing scheme is INTERNAL and protocol is TCP/UDP), set this to true
to allow packets addressed to any ports to be forwarded to the backends configured with this forwarding rule. Used with
backend service. Cannot be set if port or portRange are set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow_<wbr>global_<wbr>access</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, clients can access ILB from all regions. Otherwise only allows from the local region the ILB is located at.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A BackendService to receive the matched traffic. This is used only for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
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
scheme is INTERNAL, only TCP and UDP are valid.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is_<wbr>mirroring_<wbr>collector</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether or not this load balancer can be used as a collector for packet mirroring. To prevent mirroring loops,
instances behind this load balancer will not have their traffic mirrored even if a PacketMirroring rule applies to them.
This can only be set to true for load balancers that have their loadBalancingScheme set to INTERNAL.
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
This signifies what the ForwardingRule will be used for and can be EXTERNAL, INTERNAL, or INTERNAL_MANAGED. EXTERNAL is
used for Classic Cloud VPN gateways, protocol forwarding to VMs from an external IP address, and HTTP(S), SSL Proxy, TCP
Proxy, and Network TCP/UDP load balancers. INTERNAL is used for protocol forwarding to VMs from an internal IP address,
and internal TCP/UDP load balancers. INTERNAL_MANAGED is used for internal HTTP(S) load balancers.
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
For internal load balancing, this field identifies the network that the load balanced IP should belong to for this
Forwarding Rule. If this field is not specified, the default network will be used. This field is only used for INTERNAL
load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The networking tier used for configuring this address. This field can take the following values: PREMIUM or STANDARD. If
this field is not specified, it is assumed to be PREMIUM.
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
            <td class="align-top">ports</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field is used along with the backend_service field for internal load balancing. When the load balancing scheme is
INTERNAL, a single port or a comma separated list of ports can be configured. Only packets addressed to these ports will
be forwarded to the backends configured with this forwarding rule. You may specify a maximum of up to 5 ports.
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the region where the regional forwarding rule resides. This field is not applicable to global forwarding
rules.
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
            <td class="align-top">service_<wbr>label</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional prefix to the service name for this Forwarding Rule. If specified, will be the first label of the fully
qualified service name. The label must be 1-63 characters long, and comply with RFC1035. Specifically, the label must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The internal fully qualified service name for this Forwarding Rule. This field is only used for INTERNAL load balancing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork that the load balanced IP should belong to for this Forwarding Rule. This field is only used for INTERNAL
load balancing. If the network specified is in auto subnet mode, this field is optional. However, if the network is in
custom subnet mode, a subnetwork must be specified.
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
The URL of the target resource to receive the matched traffic. The target must live in the same region as the forwarding
rule. The forwarded traffic must be of a type appropriate to the target object.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










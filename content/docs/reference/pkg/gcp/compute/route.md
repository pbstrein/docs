
---
title: "Route"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Represents a Route resource.

A route is a rule that specifies how certain packets should be handled by
the virtual network. Routes are associated with virtual machines by tag,
and the set of routes for a particular virtual machine is called its
routing table. For each packet leaving a virtual machine, the system
searches that virtual machine's routing table for a single best matching
route.

Routes match packets by destination IP address, preferring smaller or more
specific ranges over larger ones. If there is a tie, the system selects
the route with the smallest priority value. If there is still a tie, it
uses the layer three and four packet headers to select just one of the
remaining matching routes. The packet is then forwarded as specified by
the next_hop field of the winning route -- either to another virtual
machine destination, a virtual machine gateway or a Compute
Engine-operated gateway. Packets that do not match any route in the
sending virtual machine's routing table will be dropped.

A Route resource must have exactly one specification of either
nextHopGateway, nextHopInstance, nextHopIp, nextHopVpnTunnel, or
nextHopIlb.


To get more information about Route, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/rest/v1/routes)
* How-to Guides
    * [Using Routes](https://cloud.google.com/vpc/docs/using-routes)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_route.html.markdown.



## Create a Route Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Route">Route</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouteArgs">RouteArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Route</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>dest_range=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>next_hop_gateway=None<span class="p">, </span>next_hop_ilb=None<span class="p">, </span>next_hop_instance=None<span class="p">, </span>next_hop_instance_zone=None<span class="p">, </span>next_hop_ip=None<span class="p">, </span>next_hop_vpn_tunnel=None<span class="p">, </span>priority=None<span class="p">, </span>project=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRoute<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouteArgs">RouteArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Route">Route</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Route.html">Route</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouteArgs.html">RouteArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Route resource with the given unique name, arguments, and options.

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
            <td class="align-top">Dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} 
 (Required)
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
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
            <td class="align-top">Dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} 
 (Required)
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
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
            <td class="align-top">dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} 
 (Required)
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
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
            <td class="align-top">dest_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
 (Required)
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>ilb</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>instance_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>vpn_<wbr>tunnel</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Route Output Properties

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
            <td class="align-top">Dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} (Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags to which this route applies.
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
            <td class="align-top">Dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} (Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags to which this route applies.
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
            <td class="align-top">dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} (Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags to which this route applies.
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
            <td class="align-top">dest_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
            <td class="align-top">{{% md %}} The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>ilb</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>instance_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>vpn_<wbr>tunnel</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of instance tags to which this route applies.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Route Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouteState">RouteState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Route">Route</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>dest_range=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>next_hop_gateway=None<span class="p">, </span>next_hop_ilb=None<span class="p">, </span>next_hop_instance=None<span class="p">, </span>next_hop_instance_zone=None<span class="p">, </span>next_hop_ip=None<span class="p">, </span>next_hop_network=None<span class="p">, </span>next_hop_vpn_tunnel=None<span class="p">, </span>priority=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRoute<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouteState">RouteState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Route">Route</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Route.html">Route</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouteState.html">RouteState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Route resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
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
            <td class="align-top">Dest<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
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
            <td class="align-top">dest<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Ilb</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Instance<wbr>Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next<wbr>Hop<wbr>Vpn<wbr>Tunnel</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
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
            <td class="align-top">dest_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination range of outgoing packets that this route applies to. Only IPv4 is supported.
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
Name of the resource. Provided by the client when the resource is created. The name must be 1-63 characters long, and
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
The network that this route applies to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a gateway that should handle matching packets. Currently, you can only specify the internet gateway, using a full
or partial valid URL: *
&#39;https://www.googleapis.com/compute/v1/projects/project/global/gateways/default-internet-gateway&#39; *
&#39;projects/project/global/gateways/default-internet-gateway&#39; * &#39;global/gateways/default-internet-gateway&#39; * The string
&#39;default-internet-gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>ilb</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to a forwarding rule of type loadBalancingScheme=INTERNAL that should handle matching packets. You can only
specify the forwarding rule as a partial or full URL. For example, the following are all valid URLs:
https://www.googleapis.com/compute/v1/projects/project/regions/region/forwardingRules/forwardingRule
regions/region/forwardingRules/forwardingRule Note that this can only be used when the destinationRange is a public
(non-RFC 1918) IP CIDR range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to an instance that should handle matching packets. You can specify this as a full or partial URL. For example: *
&#39;https://www.googleapis.com/compute/v1/projects/project/zones/zone/instances/instance&#39; *
&#39;projects/project/zones/zone/instances/instance&#39; * &#39;zones/zone/instances/instance&#39; * Just the instance name, with the
zone in &#39;next_hop_instance_zone&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>instance_<wbr>zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional when `next_hop_instance` is
specified)  The zone of the instance specified in
`next_hop_instance`.  Omit if `next_hop_instance` is specified as
a URL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Network IP address of an instance that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a Network that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">next_<wbr>hop_<wbr>vpn_<wbr>tunnel</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL to a VpnTunnel that should handle matching packets.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of this route. Priority is used to break ties in cases where there is more than one matching route of equal
prefix length. In the case of two routes with equal prefix length, the one with the lowest-numbered priority value wins.
Default value is 1000. Valid range is 0 through 65535.
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
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of instance tags to which this route applies.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










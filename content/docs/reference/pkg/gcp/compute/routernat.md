
---
title: "RouterNat"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A NAT service created in a router.


To get more information about RouterNat, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/rest/v1/routers)
* How-to Guides
    * [Google Cloud Router](https://cloud.google.com/router/docs/)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_router_nat.html.markdown.



## Create a RouterNat Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterNat">RouterNat</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterNatArgs">RouterNatArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">RouterNat</span><span class="p">(resource_name, opts=None, </span>drain_nat_ips=None<span class="p">, </span>icmp_idle_timeout_sec=None<span class="p">, </span>log_config=None<span class="p">, </span>min_ports_per_vm=None<span class="p">, </span>name=None<span class="p">, </span>nat_ip_allocate_option=None<span class="p">, </span>nat_ips=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>router=None<span class="p">, </span>source_subnetwork_ip_ranges_to_nat=None<span class="p">, </span>subnetworks=None<span class="p">, </span>tcp_established_idle_timeout_sec=None<span class="p">, </span>tcp_transitory_idle_timeout_sec=None<span class="p">, </span>udp_idle_timeout_sec=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRouterNat<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNatArgs">RouterNatArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNat">RouterNat</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNat.html">RouterNat</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNatArgs.html">RouterNatArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a RouterNat resource with the given unique name, arguments, and options.

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
            <td class="align-top">Drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Router<wbr>Nat<wbr>Log<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">List&lt;Router<wbr>Nat<wbr>Subnetwork<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">Drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">*Router<wbr>Nat<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">[]Router<wbr>Nat<wbr>Subnetwork</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Router<wbr>Nat<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">Router<wbr>Nat<wbr>Subnetwork[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">drain_<wbr>nat_<wbr>ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">icmp_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Dict[Router<wbr>Nat<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>ports_<wbr>per_<wbr>vm</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat_<wbr>ip_<wbr>allocate_<wbr>option</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat_<wbr>ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>subnetwork_<wbr>ip_<wbr>ranges_<wbr>to_<wbr>nat</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">List[Router<wbr>Nat<wbr>Subnetwork]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>established_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>transitory_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">udp_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## RouterNat Output Properties

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
            <td class="align-top">Drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Router<wbr>Nat<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Minimum number of ports allocated to a VM from this NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
            <td class="align-top">{{% md %}} Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">List&lt;Router<wbr>Nat<wbr>Subnetwork&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">Drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">*Router<wbr>Nat<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Minimum number of ports allocated to a VM from this NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
            <td class="align-top">{{% md %}} Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">[]Router<wbr>Nat<wbr>Subnetwork</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Router<wbr>Nat<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Minimum number of ports allocated to a VM from this NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
            <td class="align-top">{{% md %}} Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">Router<wbr>Nat<wbr>Subnetwork[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">drain_<wbr>nat_<wbr>ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">icmp_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Dict[Router<wbr>Nat<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>ports_<wbr>per_<wbr>vm</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Minimum number of ports allocated to a VM from this NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat_<wbr>ip_<wbr>allocate_<wbr>option</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat_<wbr>ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
            <td class="align-top">{{% md %}} Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>subnetwork_<wbr>ip_<wbr>ranges_<wbr>to_<wbr>nat</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">List[Router<wbr>Nat<wbr>Subnetwork]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>established_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>transitory_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">udp_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing RouterNat Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterNatState">RouterNatState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterNat">RouterNat</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>drain_nat_ips=None<span class="p">, </span>icmp_idle_timeout_sec=None<span class="p">, </span>log_config=None<span class="p">, </span>min_ports_per_vm=None<span class="p">, </span>name=None<span class="p">, </span>nat_ip_allocate_option=None<span class="p">, </span>nat_ips=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>router=None<span class="p">, </span>source_subnetwork_ip_ranges_to_nat=None<span class="p">, </span>subnetworks=None<span class="p">, </span>tcp_established_idle_timeout_sec=None<span class="p">, </span>tcp_transitory_idle_timeout_sec=None<span class="p">, </span>udp_idle_timeout_sec=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRouterNat<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNatState">RouterNatState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNat">RouterNat</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNat.html">RouterNat</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNatState.html">RouterNatState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing RouterNat resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Router<wbr>Nat<wbr>Log<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">List&lt;Router<wbr>Nat<wbr>Subnetwork<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">Drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">*Router<wbr>Nat<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">[]Router<wbr>Nat<wbr>Subnetwork</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">drain<wbr>Nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">icmp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Router<wbr>Nat<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Ports<wbr>Per<wbr>Vm</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat<wbr>Ip<wbr>Allocate<wbr>Option</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Subnetwork<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nat</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">Router<wbr>Nat<wbr>Subnetwork[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Established<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Transitory<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">udp<wbr>Idle<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
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
            <td class="align-top">drain_<wbr>nat_<wbr>ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs of the IP resources to be drained. These IPs must be valid static external IPs that have been assigned to
the NAT.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">icmp_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for ICMP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#routernatlogconfig">Dict[Router<wbr>Nat<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for logging on NAT
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>ports_<wbr>per_<wbr>vm</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Minimum number of ports allocated to a VM from this NAT.
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
Name of the NAT service. The name must be 1-63 characters long and comply with RFC1035.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat_<wbr>ip_<wbr>allocate_<wbr>option</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How external IPs should be allocated for this NAT. Valid values are &#39;AUTO_ONLY&#39; for only allowing NAT IPs allocated by
Google Cloud Platform, or &#39;MANUAL_ONLY&#39; for only user-allocated NAT IP addresses.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">nat_<wbr>ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Self-links of NAT IPs. Only valid if natIpAllocateOption is set to MANUAL_ONLY.
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
Region where the router and NAT reside.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cloud Router in which this NAT will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source_<wbr>subnetwork_<wbr>ip_<wbr>ranges_<wbr>to_<wbr>nat</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How NAT should be configured per Subnetwork. If &#39;ALL_SUBNETWORKS_ALL_IP_RANGES&#39;, all of the IP ranges in every
Subnetwork are allowed to Nat. If &#39;ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES&#39;, all of the primary IP ranges in every
Subnetwork are allowed to Nat. &#39;LIST_OF_SUBNETWORKS&#39;: A list of Subnetworks are allowed to Nat (specified in the field
subnetwork below). Note that if this field contains ALL_SUBNETWORKS_ALL_IP_RANGES or
ALL_SUBNETWORKS_ALL_PRIMARY_IP_RANGES, then there should not be any other RouterNat section in any Router for this
network in this region.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#routernatsubnetwork">List[Router<wbr>Nat<wbr>Subnetwork]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more subnetwork NAT configurations. Only used if &#39;source_subnetwork_ip_ranges_to_nat&#39; is set to
&#39;LIST_OF_SUBNETWORKS&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>established_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP established connections. Defaults to 1200s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>transitory_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for TCP transitory connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">udp_<wbr>idle_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Timeout (in seconds) for UDP connections. Defaults to 30s if not set.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### RouterNatLogConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RouterNatLogConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RouterNatLogConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNatLogConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNatLogConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNatLogConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNatLogConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Enable</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
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
            <td class="align-top">Enable</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
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
            <td class="align-top">enable</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
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
            <td class="align-top">enable</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
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





#### RouterNatSubnetwork
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RouterNatSubnetwork">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RouterNatSubnetwork">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNatSubnetworkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterNatSubnetworkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNatSubnetworkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterNatSubnetwork.html">output</a> API doc for this type.
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
            <td class="align-top">Secondary<wbr>Ip<wbr>Range<wbr>Names</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nats</td>
            <td class="align-top">
                
                <code>List<string></code>
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
            <td class="align-top">Secondary<wbr>Ip<wbr>Range<wbr>Names</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nats</td>
            <td class="align-top">
                
                <code>[]string</code>
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
            <td class="align-top">secondary<wbr>Ip<wbr>Range<wbr>Names</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nats</td>
            <td class="align-top">
                
                <code>string[]</code>
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
            <td class="align-top">secondary<wbr>Ip<wbr>Range<wbr>Names</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Ip<wbr>Ranges<wbr>To<wbr>Nats</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








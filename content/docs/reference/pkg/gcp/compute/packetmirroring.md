
---
title: "PacketMirroring"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Packet Mirroring mirrors traffic to and from particular VM instances.
You can use the collected traffic to help you detect security threats
and monitor application performance.

To get more information about PacketMirroring, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/rest/v1/packetMirroring)
* How-to Guides
    * [Using Packet Mirroring](https://cloud.google.com/vpc/docs/using-packet-mirroring#creating)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_packet_mirroring.html.markdown.



## Create a PacketMirroring Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#PacketMirroring">PacketMirroring</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#PacketMirroringArgs">PacketMirroringArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">PacketMirroring</span><span class="p">(resource_name, opts=None, </span>collector_ilb=None<span class="p">, </span>description=None<span class="p">, </span>filter=None<span class="p">, </span>mirrored_resources=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>priority=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPacketMirroring<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringArgs">PacketMirroringArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroring">PacketMirroring</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroring.html">PacketMirroring</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringArgs.html">PacketMirroringArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a PacketMirroring resource with the given unique name, arguments, and options.

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
            <td class="align-top">Collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Packet<wbr>Mirroring<wbr>Filter<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">*Packet<wbr>Mirroring<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Packet<wbr>Mirroring<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">collector_<wbr>ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Dict[Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Dict[Packet<wbr>Mirroring<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mirrored_<wbr>resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Dict[Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Dict[Packet<wbr>Mirroring<wbr>Network]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## PacketMirroring Output Properties

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
            <td class="align-top">Collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb</a></code>
            </td>
            <td class="align-top">{{% md %}} The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Packet<wbr>Mirroring<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources</a></code>
            </td>
            <td class="align-top">{{% md %}} A means of specifying which resources to mirror.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb</a></code>
            </td>
            <td class="align-top">{{% md %}} The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">*Packet<wbr>Mirroring<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources</a></code>
            </td>
            <td class="align-top">{{% md %}} A means of specifying which resources to mirror.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Priority</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb</a></code>
            </td>
            <td class="align-top">{{% md %}} The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Packet<wbr>Mirroring<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources</a></code>
            </td>
            <td class="align-top">{{% md %}} A means of specifying which resources to mirror.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">collector_<wbr>ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Dict[Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb]</a></code>
            </td>
            <td class="align-top">{{% md %}} The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Dict[Packet<wbr>Mirroring<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mirrored_<wbr>resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Dict[Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources]</a></code>
            </td>
            <td class="align-top">{{% md %}} A means of specifying which resources to mirror.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Dict[Packet<wbr>Mirroring<wbr>Network]</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing PacketMirroring Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#PacketMirroringState">PacketMirroringState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#PacketMirroring">PacketMirroring</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>collector_ilb=None<span class="p">, </span>description=None<span class="p">, </span>filter=None<span class="p">, </span>mirrored_resources=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>priority=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPacketMirroring<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringState">PacketMirroringState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroring">PacketMirroring</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroring.html">PacketMirroring</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringState.html">PacketMirroringState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing PacketMirroring resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Packet<wbr>Mirroring<wbr>Filter<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">*Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">*Packet<wbr>Mirroring<wbr>Filter</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">*Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">*Packet<wbr>Mirroring<wbr>Network</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">collector<wbr>Ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Packet<wbr>Mirroring<wbr>Filter?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mirrored<wbr>Resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Packet<wbr>Mirroring<wbr>Network?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">collector_<wbr>ilb</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringcollectorilb">Dict[Packet<wbr>Mirroring<wbr>Collector<wbr>Ilb]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Forwarding Rule resource (of type load_balancing_scheme=INTERNAL) that will be used as collector for mirrored
traffic. The specified forwarding rule must have is_mirroring_collector set to true.
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
A human-readable description of the rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringfilter">Dict[Packet<wbr>Mirroring<wbr>Filter]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A filter for mirrored traffic. If unset, all traffic is mirrored.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mirrored_<wbr>resources</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresources">Dict[Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A means of specifying which resources to mirror.
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
The name of the packet mirroring rule
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringnetwork">Dict[Packet<wbr>Mirroring<wbr>Network]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the mirrored VPC network. Only packets in this network will be mirrored. All mirrored VMs should have a NIC in
the given network. All mirrored subnetworks should belong to the given network.
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
Since only one rule can be active at a time, priority is used to break ties in the case of two rules that apply to the
same instances.
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
The Region in which the created address should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### PacketMirroringCollectorIlb
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PacketMirroringCollectorIlb">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PacketMirroringCollectorIlb">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringCollectorIlbArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringCollectorIlbOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringCollectorIlbArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringCollectorIlb.html">output</a> API doc for this type.
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
            <td class="align-top">Url</td>
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
            <td class="align-top">Url</td>
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
            <td class="align-top">url</td>
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
            <td class="align-top">url</td>
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





#### PacketMirroringFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PacketMirroringFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PacketMirroringFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringFilter.html">output</a> API doc for this type.
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
            <td class="align-top">Cidr<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocols</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Cidr<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Protocols</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">cidr<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Protocols</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">cidr<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Protocols</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### PacketMirroringMirroredResources
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PacketMirroringMirroredResources">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PacketMirroringMirroredResources">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringMirroredResourcesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringMirroredResourcesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringMirroredResourcesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringMirroredResources.html">output</a> API doc for this type.
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
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcesinstance">List&lt;Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Instance<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcessubnetwork">List&lt;Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Subnetwork<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Instances</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcesinstance">[]Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Instance</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetworks</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcessubnetwork">[]Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Subnetwork</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcesinstance">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Instance[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcessubnetwork">Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Subnetwork[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">instances</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcesinstance">List[Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Instance]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetworks</td>
            <td class="align-top">
                
                <code><a href="#packetmirroringmirroredresourcessubnetwork">List[Packet<wbr>Mirroring<wbr>Mirrored<wbr>Resources<wbr>Subnetwork]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### PacketMirroringMirroredResourcesInstance
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PacketMirroringMirroredResourcesInstance">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PacketMirroringMirroredResourcesInstance">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringMirroredResourcesInstanceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringMirroredResourcesInstanceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringMirroredResourcesInstanceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringMirroredResourcesInstance.html">output</a> API doc for this type.
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
            <td class="align-top">Url</td>
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
            <td class="align-top">Url</td>
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
            <td class="align-top">url</td>
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
            <td class="align-top">url</td>
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





#### PacketMirroringMirroredResourcesSubnetwork
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PacketMirroringMirroredResourcesSubnetwork">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PacketMirroringMirroredResourcesSubnetwork">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringMirroredResourcesSubnetworkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringMirroredResourcesSubnetworkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringMirroredResourcesSubnetworkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringMirroredResourcesSubnetwork.html">output</a> API doc for this type.
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
            <td class="align-top">Url</td>
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
            <td class="align-top">Url</td>
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
            <td class="align-top">url</td>
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
            <td class="align-top">url</td>
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





#### PacketMirroringNetwork
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PacketMirroringNetwork">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PacketMirroringNetwork">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringNetworkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#PacketMirroringNetworkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringNetworkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.PacketMirroringNetwork.html">output</a> API doc for this type.
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
            <td class="align-top">Url</td>
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
            <td class="align-top">Url</td>
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
            <td class="align-top">url</td>
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
            <td class="align-top">url</td>
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








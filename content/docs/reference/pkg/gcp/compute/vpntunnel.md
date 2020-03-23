
---
title: "VPNTunnel"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a VPNTunnel Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#VPNTunnel">VPNTunnel</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#VPNTunnelArgs">VPNTunnelArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">VPNTunnel</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>ike_version=None<span class="p">, </span>labels=None<span class="p">, </span>local_traffic_selectors=None<span class="p">, </span>name=None<span class="p">, </span>peer_external_gateway=None<span class="p">, </span>peer_external_gateway_interface=None<span class="p">, </span>peer_gcp_gateway=None<span class="p">, </span>peer_ip=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>remote_traffic_selectors=None<span class="p">, </span>router=None<span class="p">, </span>shared_secret=None<span class="p">, </span>target_vpn_gateway=None<span class="p">, </span>vpn_gateway=None<span class="p">, </span>vpn_gateway_interface=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewVPNTunnel<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#VPNTunnelArgs">VPNTunnelArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#VPNTunnel">VPNTunnel</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.VPNTunnel.html">VPNTunnel</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.VPNTunnelArgs.html">VPNTunnelArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a VPNTunnel resource with the given unique name, arguments, and options.

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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ike<wbr>Version</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ike<wbr>Version</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ike<wbr>Version</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ike_<wbr>version</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local_<wbr>traffic_<wbr>selectors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>external_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>external_<wbr>gateway_<wbr>interface</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>gcp_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remote_<wbr>traffic_<wbr>selectors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shared_<wbr>secret</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>vpn_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn_<wbr>gateway_<wbr>interface</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## VPNTunnel Output Properties

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
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detailed<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ike<wbr>Version</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
            <td class="align-top">{{% md %}} Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the peer VPN gateway. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of router resource to be used for dynamic routing.
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
            <td class="align-top">Shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shared<wbr>Secret<wbr>Hash</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tunnel<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detailed<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ike<wbr>Version</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
            <td class="align-top">{{% md %}} Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the peer VPN gateway. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of router resource to be used for dynamic routing.
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
            <td class="align-top">Shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shared<wbr>Secret<wbr>Hash</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tunnel<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detailed<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ike<wbr>Version</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
            <td class="align-top">{{% md %}} Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the peer VPN gateway. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of router resource to be used for dynamic routing.
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
            <td class="align-top">shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shared<wbr>Secret<wbr>Hash</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tunnel<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detailed_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ike_<wbr>version</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
            <td class="align-top">{{% md %}} Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local_<wbr>traffic_<wbr>selectors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>external_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>external_<wbr>gateway_<wbr>interface</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>gcp_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the peer VPN gateway. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remote_<wbr>traffic_<wbr>selectors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of router resource to be used for dynamic routing.
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
            <td class="align-top">shared_<wbr>secret</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shared_<wbr>secret_<wbr>hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>vpn_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tunnel_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn_<wbr>gateway_<wbr>interface</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The interface ID of the VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing VPNTunnel Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#VPNTunnelState">VPNTunnelState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#VPNTunnel">VPNTunnel</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>detailed_status=None<span class="p">, </span>ike_version=None<span class="p">, </span>label_fingerprint=None<span class="p">, </span>labels=None<span class="p">, </span>local_traffic_selectors=None<span class="p">, </span>name=None<span class="p">, </span>peer_external_gateway=None<span class="p">, </span>peer_external_gateway_interface=None<span class="p">, </span>peer_gcp_gateway=None<span class="p">, </span>peer_ip=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>remote_traffic_selectors=None<span class="p">, </span>router=None<span class="p">, </span>self_link=None<span class="p">, </span>shared_secret=None<span class="p">, </span>shared_secret_hash=None<span class="p">, </span>target_vpn_gateway=None<span class="p">, </span>tunnel_id=None<span class="p">, </span>vpn_gateway=None<span class="p">, </span>vpn_gateway_interface=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetVPNTunnel<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#VPNTunnelState">VPNTunnelState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#VPNTunnel">VPNTunnel</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.VPNTunnel.html">VPNTunnel</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.VPNTunnelState.html">VPNTunnelState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing VPNTunnel resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detailed<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ike<wbr>Version</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
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
            <td class="align-top">Shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shared<wbr>Secret<wbr>Hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tunnel<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Detailed<wbr>Status</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ike<wbr>Version</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
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
            <td class="align-top">Shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shared<wbr>Secret<wbr>Hash</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tunnel<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detailed<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ike<wbr>Version</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>External<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>External<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Gcp<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remote<wbr>Traffic<wbr>Selectors</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
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
            <td class="align-top">shared<wbr>Secret</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shared<wbr>Secret<wbr>Hash</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tunnel<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn<wbr>Gateway</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn<wbr>Gateway<wbr>Interface</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
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
An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">detailed_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Detailed status message for the VPN tunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ike_<wbr>version</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IKE protocol version to use when establishing the VPN tunnel with peer VPN gateway. Acceptable IKE versions are 1 or 2.
Default version is 2.
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
Labels to apply to this VpnTunnel.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local_<wbr>traffic_<wbr>selectors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Local traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
Name of the resource. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>external_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>external_<wbr>gateway_<wbr>interface</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the external VPN gateway to which this VPN tunnel is connected.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>gcp_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the peer side HA GCP VPN gateway to which this VPN tunnel is connected. If provided, the VPN tunnel will
automatically use the same vpn_gateway_interface ID in the peer GCP VPN gateway. This field must reference a
&#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the peer VPN gateway. Only IPv4 is supported.
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
The region where the tunnel is located. If unset, is set to the region of &#39;target_vpn_gateway&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remote_<wbr>traffic_<wbr>selectors</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Remote traffic selector to use when establishing the VPN tunnel with peer VPN gateway. The value should be a CIDR
formatted string, for example &#39;192.168.0.0/16&#39;. The ranges should be disjoint. Only IPv4 is supported.
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
URL of router resource to be used for dynamic routing.
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
            <td class="align-top">shared_<wbr>secret</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Shared secret used to set the secure session between the Cloud VPN gateway and the peer VPN gateway.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shared_<wbr>secret_<wbr>hash</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Hash of the shared secret.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>vpn_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the Target VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tunnel_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier for the resource. This identifier is defined by the server.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn_<wbr>gateway</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the VPN gateway with which this VPN tunnel is associated. This must be used if a High Availability VPN gateway
resource is created. This field must reference a &#39;google_compute_ha_vpn_gateway&#39; resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vpn_<wbr>gateway_<wbr>interface</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The interface ID of the VPN gateway with which this VPN tunnel is associated.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










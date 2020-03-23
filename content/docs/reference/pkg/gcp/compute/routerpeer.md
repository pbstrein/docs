
---
title: "RouterPeer"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a RouterPeer Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterPeer">RouterPeer</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterPeerArgs">RouterPeerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">RouterPeer</span><span class="p">(resource_name, opts=None, </span>advertise_mode=None<span class="p">, </span>advertised_groups=None<span class="p">, </span>advertised_ip_ranges=None<span class="p">, </span>advertised_route_priority=None<span class="p">, </span>interface=None<span class="p">, </span>name=None<span class="p">, </span>peer_asn=None<span class="p">, </span>peer_ip_address=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>router=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRouterPeer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterPeerArgs">RouterPeerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterPeer">RouterPeer</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterPeer.html">RouterPeer</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterPeerArgs.html">RouterPeerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a RouterPeer resource with the given unique name, arguments, and options.

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
            <td class="align-top">Advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">List&lt;Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name of the interface the BGP peer is associated with.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">Advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">[]Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name of the interface the BGP peer is associated with.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name of the interface the BGP peer is associated with.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">advertise_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>groups</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">List[Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>route_<wbr>priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name of the interface the BGP peer is associated with.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>asn</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## RouterPeer Output Properties

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
            <td class="align-top">Advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">List&lt;Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the interface the BGP peer is associated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">Advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">[]Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the interface the BGP peer is associated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of the interface the BGP peer is associated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">advertise_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>groups</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">List[Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>route_<wbr>priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of the interface the BGP peer is associated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>asn</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
            <td class="align-top">{{% md %}} Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cloud Router in which this BgpPeer will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing RouterPeer Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterPeerState">RouterPeerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RouterPeer">RouterPeer</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>advertise_mode=None<span class="p">, </span>advertised_groups=None<span class="p">, </span>advertised_ip_ranges=None<span class="p">, </span>advertised_route_priority=None<span class="p">, </span>interface=None<span class="p">, </span>ip_address=None<span class="p">, </span>management_type=None<span class="p">, </span>name=None<span class="p">, </span>peer_asn=None<span class="p">, </span>peer_ip_address=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>router=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRouterPeer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterPeerState">RouterPeerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterPeer">RouterPeer</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterPeer.html">RouterPeer</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterPeerState.html">RouterPeerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing RouterPeer resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">List&lt;Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the interface the BGP peer is associated with.
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
IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">Advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">[]Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the interface the BGP peer is associated with.
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
IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">advertise<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Groups</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised<wbr>Route<wbr>Priority</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the interface the BGP peer is associated with.
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
IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Asn</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
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
            <td class="align-top">advertise_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified flag to indicate which mode to use for advertisement. Valid values of this enum field are: &#39;DEFAULT&#39;,
&#39;CUSTOM&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>groups</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of prefix groups to advertise in custom mode, which can take one of the following options: *
&#39;ALL_SUBNETS&#39;: Advertises all available subnets, including peer VPC subnets. * &#39;ALL_VPC_SUBNETS&#39;: Advertises the
router&#39;s own VPC subnets. * &#39;ALL_PEER_VPC_SUBNETS&#39;: Advertises peer subnets of the router&#39;s VPC network. Note that this
field can only be populated if advertiseMode is &#39;CUSTOM&#39; and overrides the list defined for the router (in the &#34;bgp&#34;
message). These groups are advertised in addition to any specified prefixes. Leave this field blank to advertise no
custom groups.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code><a href="#routerpeeradvertisediprange">List[Router<wbr>Peer<wbr>Advertised<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User-specified list of individual IP ranges to advertise in custom mode. This field can only be populated if
advertiseMode is &#39;CUSTOM&#39; and is advertised to all peers of the router. These IP ranges will be advertised in addition
to any specified groups. Leave this field blank to advertise no custom IP ranges.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">advertised_<wbr>route_<wbr>priority</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The priority of routes advertised to this BGP peer. Where there is more than one matching route of maximum length, the
routes with the lowest priority value win.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of the interface the BGP peer is associated with.
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
IP address of the interface inside Google Cloud Platform. Only IPv4 is supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource that configures and manages this BGP peer. * &#39;MANAGED_BY_USER&#39; is the default value and can be managed by
you or other users * &#39;MANAGED_BY_ATTACHMENT&#39; is a BGP peer that is configured and managed by Cloud Interconnect,
specifically by an InterconnectAttachment of type PARTNER. Google automatically creates, updates, and deletes this type
of BGP peer when the PARTNER InterconnectAttachment is created, updated, or deleted.
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
Name of this BGP peer. The name must be 1-63 characters long, and comply with RFC1035. Specifically, the name must be
1-63 characters long and match the regular expression &#39;[a-z]([-a-z0-9]*[a-z0-9])?&#39; which means the first character must
be a lowercase letter, and all following characters must be a dash, lowercase letter, or digit, except the last
character, which cannot be a dash.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>asn</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Peer BGP Autonomous System Number (ASN). Each BGP interface may use a different value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peer_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IP address of the BGP interface outside Google Cloud Platform. Only IPv4 is supported.
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
Region where the router and BgpPeer reside. If it is not provided, the provider region is used.
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
The name of the Cloud Router in which this BgpPeer will be configured.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### RouterPeerAdvertisedIpRange
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RouterPeerAdvertisedIpRange">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RouterPeerAdvertisedIpRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterPeerAdvertisedIpRangeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RouterPeerAdvertisedIpRangeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterPeerAdvertisedIpRangeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RouterPeerAdvertisedIpRange.html">output</a> API doc for this type.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range</td>
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range</td>
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range</td>
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range</td>
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








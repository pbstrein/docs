
---
title: "ManagedZone"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a ManagedZone Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dns/#ManagedZone">ManagedZone</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dns/#ManagedZoneArgs">ManagedZoneArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ManagedZone</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>dns_name=None<span class="p">, </span>dnssec_config=None<span class="p">, </span>forwarding_config=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>peering_config=None<span class="p">, </span>private_visibility_config=None<span class="p">, </span>project=None<span class="p">, </span>reverse_lookup=None<span class="p">, </span>visibility=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewManagedZone<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneArgs">ManagedZoneArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZone">ManagedZone</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZone.html">ManagedZone</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneArgs.html">ManagedZoneArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ManagedZone resource with the given unique name, arguments, and options.

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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Managed<wbr>Zone<wbr>Dnssec<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Managed<wbr>Zone<wbr>Forwarding<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Managed<wbr>Zone<wbr>Peering<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">Reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Visibility</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">*Managed<wbr>Zone<wbr>Dnssec<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">*Managed<wbr>Zone<wbr>Forwarding<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">*Managed<wbr>Zone<wbr>Peering<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">*Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">Reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Visibility</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Managed<wbr>Zone<wbr>Dnssec<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Managed<wbr>Zone<wbr>Forwarding<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Managed<wbr>Zone<wbr>Peering<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">visibility</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dnssec_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Dict[Managed<wbr>Zone<wbr>Dnssec<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">forwarding_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Dict[Managed<wbr>Zone<wbr>Forwarding<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Dict[Managed<wbr>Zone<wbr>Peering<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>visibility_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Dict[Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">reverse_<wbr>lookup</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">visibility</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ManagedZone Output Properties

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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Managed<wbr>Zone<wbr>Dnssec<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Managed<wbr>Zone<wbr>Forwarding<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this ManagedZone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Servers</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Managed<wbr>Zone<wbr>Peering<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">Reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Visibility</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">*Managed<wbr>Zone<wbr>Dnssec<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">*Managed<wbr>Zone<wbr>Forwarding<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this ManagedZone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Servers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">*Managed<wbr>Zone<wbr>Peering<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">*Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">Reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Visibility</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Managed<wbr>Zone<wbr>Dnssec<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Managed<wbr>Zone<wbr>Forwarding<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this ManagedZone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name<wbr>Servers</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Managed<wbr>Zone<wbr>Peering<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">visibility</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
            <td class="align-top">{{% md %}} A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dnssec_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Dict[Managed<wbr>Zone<wbr>Dnssec<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">forwarding_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Dict[Managed<wbr>Zone<wbr>Forwarding<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to this ManagedZone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name_<wbr>servers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Dict[Managed<wbr>Zone<wbr>Peering<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>visibility_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Dict[Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">reverse_<wbr>lookup</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">visibility</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ManagedZone Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dns/#ManagedZoneState">ManagedZoneState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dns/#ManagedZone">ManagedZone</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>dns_name=None<span class="p">, </span>dnssec_config=None<span class="p">, </span>forwarding_config=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>name_servers=None<span class="p">, </span>peering_config=None<span class="p">, </span>private_visibility_config=None<span class="p">, </span>project=None<span class="p">, </span>reverse_lookup=None<span class="p">, </span>visibility=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetManagedZone<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneState">ManagedZoneState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZone">ManagedZone</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZone.html">ManagedZone</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneState.html">ManagedZoneState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ManagedZone resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Managed<wbr>Zone<wbr>Dnssec<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Managed<wbr>Zone<wbr>Forwarding<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Servers</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Managed<wbr>Zone<wbr>Peering<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">Reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Visibility</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">*Managed<wbr>Zone<wbr>Dnssec<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">*Managed<wbr>Zone<wbr>Forwarding<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Servers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">*Managed<wbr>Zone<wbr>Peering<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">*Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">Reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Visibility</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dnssec<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Managed<wbr>Zone<wbr>Dnssec<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">forwarding<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Managed<wbr>Zone<wbr>Forwarding<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name<wbr>Servers</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Managed<wbr>Zone<wbr>Peering<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Visibility<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">reverse<wbr>Lookup</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">visibility</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
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
A textual description field. Defaults to &#39;Managed by Terraform&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The DNS name of this managed zone, for instance &#34;example.com.&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dnssec_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfig">Dict[Managed<wbr>Zone<wbr>Dnssec<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNSSEC configuration
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">forwarding_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfig">Dict[Managed<wbr>Zone<wbr>Forwarding<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence for this field indicates that outbound forwarding is enabled for this zone. The value of this field
contains the set of destinations to forward to.
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
A set of key/value label pairs to assign to this ManagedZone.
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
User assigned name for this resource. Must be unique within the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name_<wbr>servers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Delegate your managed_zone to these virtual name servers; defined by the server
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfig">Dict[Managed<wbr>Zone<wbr>Peering<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The presence of this field indicates that DNS Peering is enabled for this zone. The value of this field contains the
network to peer with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>visibility_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfig">Dict[Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
For privately visible zones, the set of Virtual Private Cloud resources that the zone is visible from.
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
            <td class="align-top">reverse_<wbr>lookup</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies if this is a managed reverse lookup zone. If true, Cloud DNS will resolve reverse lookup queries using
automatically configured records for VPC resources. This only applies to networks listed under
&#39;private_visibility_config&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">visibility</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone&#39;s visibility: public zones are exposed to the Internet, while private zones are visible only to Virtual Private
Cloud resources. Must be one of: &#39;public&#39;, &#39;private&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ManagedZoneDnssecConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZoneDnssecConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZoneDnssecConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneDnssecConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneDnssecConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneDnssecConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneDnssecConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Default<wbr>Key<wbr>Specs</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfigdefaultkeyspec">List&lt;Managed<wbr>Zone<wbr>Dnssec<wbr>Config<wbr>Default<wbr>Key<wbr>Spec<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kind</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Non<wbr>Existence</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">Default<wbr>Key<wbr>Specs</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfigdefaultkeyspec">[]Managed<wbr>Zone<wbr>Dnssec<wbr>Config<wbr>Default<wbr>Key<wbr>Spec</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kind</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Non<wbr>Existence</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>*string</code>
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
            <td class="align-top">default<wbr>Key<wbr>Specs</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfigdefaultkeyspec">Managed<wbr>Zone<wbr>Dnssec<wbr>Config<wbr>Default<wbr>Key<wbr>Spec[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kind</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">non<wbr>Existence</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">default<wbr>Key<wbr>Specs</td>
            <td class="align-top">
                
                <code><a href="#managedzonednssecconfigdefaultkeyspec">List[Managed<wbr>Zone<wbr>Dnssec<wbr>Config<wbr>Default<wbr>Key<wbr>Spec]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kind</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">non<wbr>Existence</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ManagedZoneDnssecConfigDefaultKeySpec
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZoneDnssecConfigDefaultKeySpec">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZoneDnssecConfigDefaultKeySpec">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneDnssecConfigDefaultKeySpecArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneDnssecConfigDefaultKeySpecOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneDnssecConfigDefaultKeySpecArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneDnssecConfigDefaultKeySpec.html">output</a> API doc for this type.
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Length</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kind</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">Algorithm</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Length</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kind</td>
            <td class="align-top">
                
                <code>*string</code>
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Length</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kind</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">algorithm</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Length</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kind</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ManagedZoneForwardingConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZoneForwardingConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZoneForwardingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneForwardingConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneForwardingConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneForwardingConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneForwardingConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Target<wbr>Name<wbr>Servers</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfigtargetnameserver">List&lt;Managed<wbr>Zone<wbr>Forwarding<wbr>Config<wbr>Target<wbr>Name<wbr>Server<wbr>Args&gt;</a></code>
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
            <td class="align-top">Target<wbr>Name<wbr>Servers</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfigtargetnameserver">[]Managed<wbr>Zone<wbr>Forwarding<wbr>Config<wbr>Target<wbr>Name<wbr>Server</a></code>
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
            <td class="align-top">target<wbr>Name<wbr>Servers</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfigtargetnameserver">Managed<wbr>Zone<wbr>Forwarding<wbr>Config<wbr>Target<wbr>Name<wbr>Server[]</a></code>
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
            <td class="align-top">target<wbr>Name<wbr>Servers</td>
            <td class="align-top">
                
                <code><a href="#managedzoneforwardingconfigtargetnameserver">List[Managed<wbr>Zone<wbr>Forwarding<wbr>Config<wbr>Target<wbr>Name<wbr>Server]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ManagedZoneForwardingConfigTargetNameServer
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZoneForwardingConfigTargetNameServer">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZoneForwardingConfigTargetNameServer">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneForwardingConfigTargetNameServerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZoneForwardingConfigTargetNameServerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneForwardingConfigTargetNameServerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZoneForwardingConfigTargetNameServer.html">output</a> API doc for this type.
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
            <td class="align-top">Forwarding<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ipv4Address</td>
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
            <td class="align-top">Forwarding<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ipv4Address</td>
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
            <td class="align-top">forwarding<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ipv4Address</td>
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
            <td class="align-top">forwarding<wbr>Path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ipv4Address</td>
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





#### ManagedZonePeeringConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZonePeeringConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZonePeeringConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePeeringConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePeeringConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePeeringConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePeeringConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Target<wbr>Network</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfigtargetnetwork">Managed<wbr>Zone<wbr>Peering<wbr>Config<wbr>Target<wbr>Network<wbr>Args</a></code>
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
            <td class="align-top">Target<wbr>Network</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfigtargetnetwork">Managed<wbr>Zone<wbr>Peering<wbr>Config<wbr>Target<wbr>Network</a></code>
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
            <td class="align-top">target<wbr>Network</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfigtargetnetwork">Managed<wbr>Zone<wbr>Peering<wbr>Config<wbr>Target<wbr>Network</a></code>
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
            <td class="align-top">target<wbr>Network</td>
            <td class="align-top">
                
                <code><a href="#managedzonepeeringconfigtargetnetwork">Dict[Managed<wbr>Zone<wbr>Peering<wbr>Config<wbr>Target<wbr>Network]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ManagedZonePeeringConfigTargetNetwork
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZonePeeringConfigTargetNetwork">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZonePeeringConfigTargetNetwork">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePeeringConfigTargetNetworkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePeeringConfigTargetNetworkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePeeringConfigTargetNetworkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePeeringConfigTargetNetwork.html">output</a> API doc for this type.
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
            <td class="align-top">Network<wbr>Url</td>
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
            <td class="align-top">Network<wbr>Url</td>
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
            <td class="align-top">network<wbr>Url</td>
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
            <td class="align-top">network<wbr>Url</td>
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





#### ManagedZonePrivateVisibilityConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZonePrivateVisibilityConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZonePrivateVisibilityConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePrivateVisibilityConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePrivateVisibilityConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePrivateVisibilityConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePrivateVisibilityConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Networks</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfignetwork">List&lt;Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config<wbr>Network<wbr>Args&gt;</a></code>
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
            <td class="align-top">Networks</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfignetwork">[]Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config<wbr>Network</a></code>
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
            <td class="align-top">networks</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfignetwork">Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config<wbr>Network[]</a></code>
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
            <td class="align-top">networks</td>
            <td class="align-top">
                
                <code><a href="#managedzoneprivatevisibilityconfignetwork">List[Managed<wbr>Zone<wbr>Private<wbr>Visibility<wbr>Config<wbr>Network]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ManagedZonePrivateVisibilityConfigNetwork
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ManagedZonePrivateVisibilityConfigNetwork">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ManagedZonePrivateVisibilityConfigNetwork">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePrivateVisibilityConfigNetworkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dns?tab=doc#ManagedZonePrivateVisibilityConfigNetworkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePrivateVisibilityConfigNetworkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dns.ManagedZonePrivateVisibilityConfigNetwork.html">output</a> API doc for this type.
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
            <td class="align-top">Network<wbr>Url</td>
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
            <td class="align-top">Network<wbr>Url</td>
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
            <td class="align-top">network<wbr>Url</td>
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
            <td class="align-top">network<wbr>Url</td>
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








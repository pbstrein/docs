
---
title: "InterconnectAttachment"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a InterconnectAttachment Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#InterconnectAttachment">InterconnectAttachment</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#InterconnectAttachmentArgs">InterconnectAttachmentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">InterconnectAttachment</span><span class="p">(resource_name, opts=None, </span>admin_enabled=None<span class="p">, </span>bandwidth=None<span class="p">, </span>candidate_subnets=None<span class="p">, </span>description=None<span class="p">, </span>edge_availability_domain=None<span class="p">, </span>interconnect=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>router=None<span class="p">, </span>type=None<span class="p">, </span>vlan_tag8021q=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewInterconnectAttachment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#InterconnectAttachmentArgs">InterconnectAttachmentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#InterconnectAttachment">InterconnectAttachment</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.InterconnectAttachment.html">InterconnectAttachment</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.InterconnectAttachmentArgs.html">InterconnectAttachmentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a InterconnectAttachment resource with the given unique name, arguments, and options.

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
            <td class="align-top">Admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bandwidth</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
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
            <td class="align-top">Edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interconnect</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">Admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bandwidth</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
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
            <td class="align-top">Edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interconnect</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bandwidth</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
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
            <td class="align-top">edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interconnect</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">admin_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bandwidth</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">candidate_<wbr>subnets</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
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
            <td class="align-top">edge_<wbr>availability_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interconnect</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vlan_<wbr>tag8021q</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## InterconnectAttachment Output Properties

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
            <td class="align-top">Admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bandwidth</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cloud<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">Customer<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">Edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Reference<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interconnect</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">Pairing<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partner<wbr>Asn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Interconnect<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
            <td class="align-top">{{% md %}} Region where the regional interconnect attachment resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">Admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bandwidth</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cloud<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">Customer<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">Edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Reference<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interconnect</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">Pairing<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partner<wbr>Asn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Interconnect<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
            <td class="align-top">{{% md %}} Region where the regional interconnect attachment resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bandwidth</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cloud<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">customer<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google<wbr>Reference<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interconnect</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">pairing<wbr>Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partner<wbr>Asn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Interconnect<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
            <td class="align-top">{{% md %}} Region where the regional interconnect attachment resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} [Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">admin_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bandwidth</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">candidate_<wbr>subnets</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cloud_<wbr>router_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">customer_<wbr>router_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">edge_<wbr>availability_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google_<wbr>reference_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interconnect</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">pairing_<wbr>key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partner_<wbr>asn</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>interconnect_<wbr>info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Dict[Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info]</a></code>
            </td>
            <td class="align-top">{{% md %}} Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
            <td class="align-top">{{% md %}} Region where the regional interconnect attachment resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">router</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} [Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vlan_<wbr>tag8021q</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing InterconnectAttachment Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#InterconnectAttachmentState">InterconnectAttachmentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#InterconnectAttachment">InterconnectAttachment</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>admin_enabled=None<span class="p">, </span>bandwidth=None<span class="p">, </span>candidate_subnets=None<span class="p">, </span>cloud_router_ip_address=None<span class="p">, </span>creation_timestamp=None<span class="p">, </span>customer_router_ip_address=None<span class="p">, </span>description=None<span class="p">, </span>edge_availability_domain=None<span class="p">, </span>google_reference_id=None<span class="p">, </span>interconnect=None<span class="p">, </span>name=None<span class="p">, </span>pairing_key=None<span class="p">, </span>partner_asn=None<span class="p">, </span>private_interconnect_info=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>router=None<span class="p">, </span>self_link=None<span class="p">, </span>state=None<span class="p">, </span>type=None<span class="p">, </span>vlan_tag8021q=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetInterconnectAttachment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#InterconnectAttachmentState">InterconnectAttachmentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#InterconnectAttachment">InterconnectAttachment</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.InterconnectAttachment.html">InterconnectAttachment</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.InterconnectAttachmentState.html">InterconnectAttachmentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing InterconnectAttachment resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bandwidth</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cloud<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">Customer<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">Edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Reference<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interconnect</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">Pairing<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partner<wbr>Asn</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Interconnect<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">Admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bandwidth</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cloud<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">Customer<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">Edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Reference<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interconnect</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">Pairing<wbr>Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partner<wbr>Asn</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Interconnect<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">*Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">admin<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bandwidth</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">candidate<wbr>Subnets</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cloud<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">customer<wbr>Router<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">edge<wbr>Availability<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google<wbr>Reference<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interconnect</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">pairing<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partner<wbr>Asn</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Interconnect<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vlan<wbr>Tag8021q</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
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
            <td class="align-top">admin_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the VLAN attachment is enabled or disabled. When using PARTNER type this will Pre-Activate the interconnect
attachment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bandwidth</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Provisioned bandwidth capacity for the interconnect attachment. For attachments of type DEDICATED, the user can set the
bandwidth. For attachments of type PARTNER, the Google Partner that is operating the interconnect must set the
bandwidth. Output only for PARTNER type, mutable for PARTNER_PROVIDER and DEDICATED, Defaults to BPS_10G
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">candidate_<wbr>subnets</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Up to 16 candidate prefixes that can be used to restrict the allocation of cloudRouterIpAddress and
customerRouterIpAddress for this attachment. All prefixes must be within link-local address space (169.254.0.0/16) and
must be /29 or shorter (/28, /27, etc). Google will attempt to select an unused /29 from the supplied candidate
prefix(es). The request will fail if all possible /29s are in use on Google&#39;s edge. If not supplied, Google will
randomly select an unused /29 from all of link-local space.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cloud_<wbr>router_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on Cloud Router Interface for this interconnect attachment.
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
            <td class="align-top">customer_<wbr>router_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
IPv4 address &#43; prefix length to be configured on the customer router subinterface for this interconnect attachment.
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
            <td class="align-top">edge_<wbr>availability_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired availability domain for the attachment. Only available for type PARTNER, at creation time. For improved
reliability, customers should configure a pair of attachments with one per availability domain. The selected
availability domain will be provided to the Partner via the pairing key so that the provisioned circuit will lie in the
specified domain. If not specified, the value will default to AVAILABILITY_DOMAIN_ANY.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google_<wbr>reference_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Google reference ID, to be used when raising support tickets with Google or otherwise to debug backend connectivity
issues.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interconnect</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
URL of the underlying Interconnect object that this attachment&#39;s traffic will traverse through. Required if type is
DEDICATED, must not be set if type is PARTNER.
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
            <td class="align-top">pairing_<wbr>key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. The opaque identifier of an PARTNER attachment used to
initiate provisioning with a selected partner. Of the form &#34;XXXXX/region/domain&#34;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partner_<wbr>asn</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output only for type PARTNER. Not present for DEDICATED]. Optional BGP ASN for the router that should be supplied by a
layer 3 Partner if they configured BGP on behalf of the customer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>interconnect_<wbr>info</td>
            <td class="align-top">
                
                <code><a href="#interconnectattachmentprivateinterconnectinfo">Dict[Interconnect<wbr>Attachment<wbr>Private<wbr>Interconnect<wbr>Info]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Information specific to an InterconnectAttachment. This property is populated if the interconnect that this is attached
to is of type DEDICATED.
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
Region where the regional interconnect attachment resides.
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
URL of the cloud router to be used for dynamic routing. This router must be in the same region as this
InterconnectAttachment. The InterconnectAttachment will automatically connect the Interconnect to the network &amp; region
within which the Cloud Router is configured.
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
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
[Output Only] The current state of this attachment&#39;s functionality.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The type of InterconnectAttachment you wish to create. Defaults to DEDICATED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vlan_<wbr>tag8021q</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IEEE 802.1Q VLAN tag for this attachment, in the range 2-4094. When using PARTNER type this will be managed
upstream.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### InterconnectAttachmentPrivateInterconnectInfo
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#InterconnectAttachmentPrivateInterconnectInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#InterconnectAttachmentPrivateInterconnectInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.InterconnectAttachmentPrivateInterconnectInfo.html">output</a> API doc for this type.
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
            <td class="align-top">Tag8021q</td>
            <td class="align-top">
                
                <code>int?</code>
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
            <td class="align-top">Tag8021q</td>
            <td class="align-top">
                
                <code>*int</code>
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
            <td class="align-top">tag8021q</td>
            <td class="align-top">
                
                <code>number?</code>
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
            <td class="align-top">tag8021q</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








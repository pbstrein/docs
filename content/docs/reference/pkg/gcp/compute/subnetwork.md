
---
title: "Subnetwork"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A VPC network is a virtual version of the traditional physical networks
that exist within and between physical data centers. A VPC network
provides connectivity for your Compute Engine virtual machine (VM)
instances, Container Engine containers, App Engine Flex services, and
other network-related resources.

Each GCP project contains one or more VPC networks. Each VPC network is a
global entity spanning all GCP regions. This global VPC network allows VM
instances and other resources to communicate with each other via internal,
private IP addresses.

Each VPC network is subdivided into subnets, and each subnet is contained
within a single region. You can have more than one subnet in a region for
a given VPC network. Each subnet has a contiguous private RFC1918 IP
space. You create instances, containers, and the like in these subnets.
When you create an instance, you must create it in a subnet, and the
instance draws its internal IP address from that subnet.

Virtual machine (VM) instances in a VPC network can communicate with
instances in all other subnets of the same VPC network, regardless of
region, using their RFC1918 private IP addresses. You can isolate portions
of the network, even entire subnets, using firewall rules.


To get more information about Subnetwork, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/rest/beta/subnetworks)
* How-to Guides
    * [Private Google Access](https://cloud.google.com/vpc/docs/configure-private-google-access)
    * [Cloud Networking](https://cloud.google.com/vpc/docs/using-vpc)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_subnetwork.html.markdown.



## Create a Subnetwork Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Subnetwork">Subnetwork</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SubnetworkArgs">SubnetworkArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Subnetwork</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>ip_cidr_range=None<span class="p">, </span>log_config=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>private_ip_google_access=None<span class="p">, </span>project=None<span class="p">, </span>purpose=None<span class="p">, </span>region=None<span class="p">, </span>role=None<span class="p">, </span>secondary_ip_ranges=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSubnetwork<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SubnetworkArgs">SubnetworkArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Subnetwork">Subnetwork</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Subnetwork.html">Subnetwork</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SubnetworkArgs.html">SubnetworkArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Subnetwork resource with the given unique name, arguments, and options.

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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Subnetwork<wbr>Log<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">List&lt;Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">*Subnetwork<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">[]Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Subnetwork<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>cidr_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Dict[Subnetwork<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>ip_<wbr>google_<wbr>access</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">List[Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Subnetwork Output Properties

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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Subnetwork<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
            <td class="align-top">{{% md %}} The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">List&lt;Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">*Subnetwork<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
            <td class="align-top">{{% md %}} The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">[]Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Subnetwork<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
            <td class="align-top">{{% md %}} The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range[]</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>cidr_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Dict[Subnetwork<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
            <td class="align-top">{{% md %}} The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>ip_<wbr>google_<wbr>access</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">List[Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Subnetwork Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SubnetworkState">SubnetworkState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#Subnetwork">Subnetwork</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>fingerprint=None<span class="p">, </span>gateway_address=None<span class="p">, </span>ip_cidr_range=None<span class="p">, </span>log_config=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>private_ip_google_access=None<span class="p">, </span>project=None<span class="p">, </span>purpose=None<span class="p">, </span>region=None<span class="p">, </span>role=None<span class="p">, </span>secondary_ip_ranges=None<span class="p">, </span>self_link=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSubnetwork<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SubnetworkState">SubnetworkState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#Subnetwork">Subnetwork</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.Subnetwork.html">Subnetwork</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SubnetworkState.html">SubnetworkState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Subnetwork resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Subnetwork<wbr>Log<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">List&lt;Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">*Subnetwork<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">Purpose</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">[]Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Subnetwork<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Ip<wbr>Google<wbr>Access</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
An optional description of this resource. Provide this property when you create the resource. This field can be set only
at resource creation time.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Fingerprint of this resource. This field is used internally during updates of this resource.
 {{% /md %}}

            This field is not useful for users, and has been removed as an output.
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The gateway address for default routes to reach destination addresses outside this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>cidr_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The range of internal addresses that are owned by this subnetwork. Provide this property when you create the subnetwork.
For example, 10.0.0.0/8 or 192.168.0.0/16. Ranges must be unique and non-overlapping within a network. Only IPv4 is
supported.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#subnetworklogconfig">Dict[Subnetwork<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Denotes the logging options for the subnetwork flow logs. If logging is enabled logs will be exported to Stackdriver.
This field cannot be set if the &#39;purpose&#39; of this subnetwork is &#39;INTERNAL_HTTPS_LOAD_BALANCER&#39;
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
The name of the resource, provided by the client when initially creating the resource. The name must be 1-63 characters
long, and comply with RFC1035. Specifically, the name must be 1-63 characters long and match the regular expression
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
The network this subnet belongs to. Only networks that are in the distributed mode can have subnetworks.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>ip_<wbr>google_<wbr>access</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When enabled, VMs in this subnetwork without external IP addresses can access Google APIs and services by using Private
Google Access.
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
            <td class="align-top">purpose</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The purpose of the resource. This field can be either PRIVATE or INTERNAL_HTTPS_LOAD_BALANCER. A subnetwork with purpose
set to INTERNAL_HTTPS_LOAD_BALANCER is a user-created subnetwork that is reserved for Internal HTTP(S) Load Balancing.
If unspecified, the purpose defaults to PRIVATE. If set to INTERNAL_HTTPS_LOAD_BALANCER you must also set the role.
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
URL of the GCP region for this subnetwork.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role of subnetwork. Currently, this field is only used when purpose = INTERNAL_HTTPS_LOAD_BALANCER. The value can be
set to ACTIVE or BACKUP. An ACTIVE subnetwork is one that is currently being used for Internal HTTP(S) Load Balancing. A
BACKUP subnetwork is one that is ready to be promoted to ACTIVE or is currently draining.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code><a href="#subnetworksecondaryiprange">List[Subnetwork<wbr>Secondary<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of configurations for secondary IP ranges for VM instances contained in this subnetwork. The primary IP of such
VM must belong to the primary ipCidrRange of the subnetwork. The alias IPs may belong to either primary or secondary
ranges. **Note**: This field uses [attr-as-block mode](https://www.terraform.io/docs/configuration/attr-as-blocks.html)
to avoid breaking users during the 0.12 upgrade. To explicitly send a list of zero objects you must use the following
syntax: &#39;example=[]&#39; For more details about this behavior, see [this
section](https://www.terraform.io/docs/configuration/attr-as-blocks.html#defining-a-fixed-object-collection-value).
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
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### SubnetworkLogConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SubnetworkLogConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SubnetworkLogConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SubnetworkLogConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SubnetworkLogConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SubnetworkLogConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SubnetworkLogConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Aggregation<wbr>Interval</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Flow<wbr>Sampling</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
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
            <td class="align-top">Aggregation<wbr>Interval</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Flow<wbr>Sampling</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
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
            <td class="align-top">aggregation<wbr>Interval</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">flow<wbr>Sampling</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
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
            <td class="align-top">aggregation<wbr>Interval</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">flow<wbr>Sampling</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
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





#### SubnetworkSecondaryIpRange
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SubnetworkSecondaryIpRange">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SubnetworkSecondaryIpRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SubnetworkSecondaryIpRangeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SubnetworkSecondaryIpRangeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SubnetworkSecondaryIpRangeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SubnetworkSecondaryIpRange.html">output</a> API doc for this type.
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
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Name</td>
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
            <td class="align-top">Ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Name</td>
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
            <td class="align-top">ip<wbr>Cidr<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range<wbr>Name</td>
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
            <td class="align-top">ip_<wbr>cidr_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range<wbr>Name</td>
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








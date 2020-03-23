
---
title: "RegionInstanceGroupManager"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

The Google Compute Engine Regional Instance Group Manager API creates and manages pools
of homogeneous Compute Engine virtual machine instances from a common instance
template. For more information, see [the official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups)
and [API](https://cloud.google.com/compute/docs/reference/latest/regionInstanceGroupManagers)

> **Note:** Use [gcp.compute.InstanceGroupManager](https://www.terraform.io/docs/providers/google/r/compute_instance_group_manager.html) to create a single-zone instance group manager.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_region_instance_group_manager.html.markdown.



## Create a RegionInstanceGroupManager Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionInstanceGroupManager">RegionInstanceGroupManager</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionInstanceGroupManagerArgs">RegionInstanceGroupManagerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">RegionInstanceGroupManager</span><span class="p">(resource_name, opts=None, </span>auto_healing_policies=None<span class="p">, </span>base_instance_name=None<span class="p">, </span>description=None<span class="p">, </span>distribution_policy_zones=None<span class="p">, </span>name=None<span class="p">, </span>named_ports=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>target_pools=None<span class="p">, </span>target_size=None<span class="p">, </span>update_policy=None<span class="p">, </span>versions=None<span class="p">, </span>wait_for_instances=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRegionInstanceGroupManager<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerArgs">RegionInstanceGroupManagerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManager">RegionInstanceGroupManager</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManager.html">RegionInstanceGroupManager</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerArgs.html">RegionInstanceGroupManagerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a RegionInstanceGroupManager resource with the given unique name, arguments, and options.

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
            <td class="align-top">Auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">List&lt;Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Pools</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">List&lt;Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">Auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">*Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">[]Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Pools</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">*Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">[]Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Pools</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Size</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">auto_<wbr>healing_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">base_<wbr>instance_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">distribution_<wbr>policy_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">named_<wbr>ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">List[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>pools</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">List[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait_<wbr>for_<wbr>instances</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## RegionInstanceGroupManager Output Properties

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
            <td class="align-top">Auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies?</a></code>
            </td>
            <td class="align-top">{{% md %}} The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of the instance group created by the manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">List&lt;Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The named port configuration. See the section below
for details on configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Pools</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">List&lt;Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">Auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">*Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies</a></code>
            </td>
            <td class="align-top">{{% md %}} The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of the instance group created by the manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">[]Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port</a></code>
            </td>
            <td class="align-top">{{% md %}} The named port configuration. See the section below
for details on configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Pools</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">[]Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version</a></code>
            </td>
            <td class="align-top">{{% md %}} Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies?</a></code>
            </td>
            <td class="align-top">{{% md %}} The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of the instance group created by the manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The named port configuration. See the section below
for details on configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Pools</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Size</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version[]</a></code>
            </td>
            <td class="align-top">{{% md %}} Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">auto_<wbr>healing_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies]</a></code>
            </td>
            <td class="align-top">{{% md %}} The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">base_<wbr>instance_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">distribution_<wbr>policy_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of the instance group created by the manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">named_<wbr>ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">List[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port]</a></code>
            </td>
            <td class="align-top">{{% md %}} The named port configuration. See the section below
for details on configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The region where the managed instance group resides.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>pools</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">List[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version]</a></code>
            </td>
            <td class="align-top">{{% md %}} Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait_<wbr>for_<wbr>instances</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing RegionInstanceGroupManager Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionInstanceGroupManagerState">RegionInstanceGroupManagerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionInstanceGroupManager">RegionInstanceGroupManager</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>auto_healing_policies=None<span class="p">, </span>base_instance_name=None<span class="p">, </span>description=None<span class="p">, </span>distribution_policy_zones=None<span class="p">, </span>fingerprint=None<span class="p">, </span>instance_group=None<span class="p">, </span>name=None<span class="p">, </span>named_ports=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>self_link=None<span class="p">, </span>target_pools=None<span class="p">, </span>target_size=None<span class="p">, </span>update_policy=None<span class="p">, </span>versions=None<span class="p">, </span>wait_for_instances=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRegionInstanceGroupManager<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerState">RegionInstanceGroupManagerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManager">RegionInstanceGroupManager</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManager.html">RegionInstanceGroupManager</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerState.html">RegionInstanceGroupManagerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing RegionInstanceGroupManager resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of the instance group created by the manager.
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">List&lt;Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
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
The region where the managed instance group resides.
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
The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Pools</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">List&lt;Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">Auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">*Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of the instance group created by the manager.
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">[]Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
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
The region where the managed instance group resides.
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
The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Pools</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">*Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">[]Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">auto<wbr>Healing<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">base<wbr>Instance<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">distribution<wbr>Policy<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of the instance group created by the manager.
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">named<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
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
The region where the managed instance group resides.
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
The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Pools</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Size</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait<wbr>For<wbr>Instances</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
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
            <td class="align-top">auto_<wbr>healing_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerautohealingpolicies">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Auto<wbr>Healing<wbr>Policies]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The autohealing policies for this managed instance
group. You can specify only one value. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/creating-groups-of-managed-instances#monitoring_groups).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">base_<wbr>instance_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The base instance name to use for
instances in this group. The value must be a valid
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt) name. Supported characters
are lowercase letters, numbers, and hyphens (-). Instances are named by
appending a hyphen and a random four-character string to the base instance
name.
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
An optional textual description of the instance
group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">distribution_<wbr>policy_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The distribution policy for this managed instance
group. You can specify one or more values. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/distributing-instances-with-regional-instance-groups#selectingzones).
- - -
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
The fingerprint of the instance group manager.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of the instance group created by the manager.
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">named_<wbr>ports</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagernamedport">List[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Named<wbr>Port]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The named port configuration. See the section below
for details on configuration.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
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
The region where the managed instance group resides.
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
The URL of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>pools</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full URL of all target pools to which new
instances in the group are added. Updating the target pools attribute does
not affect existing instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">update_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerupdatepolicy">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Update<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The update policy for this managed instance group. Structure is documented below. For more information, see the [official documentation](https://cloud.google.com/compute/docs/instance-groups/updating-managed-instance-groups) and [API](https://cloud.google.com/compute/docs/reference/rest/beta/regionInstanceGroupManagers/patch)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">versions</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversion">List[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Application versions managed by this instance group. Each
version deals with a specific instance template, allowing canary release scenarios.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">wait_<wbr>for_<wbr>instances</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to wait for all instances to be created/updated before
returning. Note that if this is set to true and the operation does not succeed, this provider will
continue trying until it times out.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### RegionInstanceGroupManagerAutoHealingPolicies
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionInstanceGroupManagerAutoHealingPolicies">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionInstanceGroupManagerAutoHealingPolicies">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerAutoHealingPoliciesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerAutoHealingPoliciesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerAutoHealingPoliciesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerAutoHealingPolicies.html">output</a> API doc for this type.
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
            <td class="align-top">Health<wbr>Check</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Delay<wbr>Sec</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">Health<wbr>Check</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Delay<wbr>Sec</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">health<wbr>Check</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial<wbr>Delay<wbr>Sec</td>
            <td class="align-top">
                
                <code>number</code>
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
            <td class="align-top">health<wbr>Check</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial<wbr>Delay<wbr>Sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### RegionInstanceGroupManagerNamedPort
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionInstanceGroupManagerNamedPort">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionInstanceGroupManagerNamedPort">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerNamedPortArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerNamedPortOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerNamedPortArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerNamedPort.html">output</a> API doc for this type.
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number</code>
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### RegionInstanceGroupManagerUpdatePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionInstanceGroupManagerUpdatePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionInstanceGroupManagerUpdatePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerUpdatePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerUpdatePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerUpdatePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerUpdatePolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Instance<wbr>Redistribution<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Surge<wbr>Fixed</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Surge<wbr>Percent</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unavailable<wbr>Fixed</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unavailable<wbr>Percent</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ready<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimal<wbr>Action</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
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
            <td class="align-top">Instance<wbr>Redistribution<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Surge<wbr>Fixed</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Surge<wbr>Percent</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unavailable<wbr>Fixed</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unavailable<wbr>Percent</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Ready<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimal<wbr>Action</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
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
            <td class="align-top">instance<wbr>Redistribution<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Surge<wbr>Fixed</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Surge<wbr>Percent</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unavailable<wbr>Fixed</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unavailable<wbr>Percent</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Ready<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimal<wbr>Action</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
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
            <td class="align-top">instance<wbr>Redistribution<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Surge<wbr>Fixed</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Surge<wbr>Percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unavailable<wbr>Fixed</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unavailable<wbr>Percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Ready<wbr>Sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimal<wbr>Action</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
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





#### RegionInstanceGroupManagerVersion
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionInstanceGroupManagerVersion">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionInstanceGroupManagerVersion">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerVersionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerVersionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerVersionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerVersion.html">output</a> API doc for this type.
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
            <td class="align-top">Instance<wbr>Template</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversiontargetsize">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version<wbr>Target<wbr>Size<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
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
            <td class="align-top">Instance<wbr>Template</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Size</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversiontargetsize">*Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version<wbr>Target<wbr>Size</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
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
            <td class="align-top">instance<wbr>Template</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Size</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversiontargetsize">Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version<wbr>Target<wbr>Size?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
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
            <td class="align-top">instance<wbr>Template</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
The name of the instance group manager. Must be 1-63
characters long and comply with
[RFC1035](https://www.ietf.org/rfc/rfc1035.txt). Supported characters
include lowercase letters, numbers, and hyphens.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>size</td>
            <td class="align-top">
                
                <code><a href="#regioninstancegroupmanagerversiontargetsize">Dict[Region<wbr>Instance<wbr>Group<wbr>Manager<wbr>Version<wbr>Target<wbr>Size]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The target number of running instances for this managed
instance group. This value should always be explicitly set unless this resource is attached to
an autoscaler, in which case it should never be set. Defaults to `0`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### RegionInstanceGroupManagerVersionTargetSize
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionInstanceGroupManagerVersionTargetSize">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionInstanceGroupManagerVersionTargetSize">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerVersionTargetSizeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionInstanceGroupManagerVersionTargetSizeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerVersionTargetSizeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionInstanceGroupManagerVersionTargetSize.html">output</a> API doc for this type.
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
            <td class="align-top">Fixed</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Percent</td>
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
            <td class="align-top">Fixed</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Percent</td>
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
            <td class="align-top">fixed</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">percent</td>
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
            <td class="align-top">fixed</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">percent</td>
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








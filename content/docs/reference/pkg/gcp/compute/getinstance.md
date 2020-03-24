
---
title: "GetInstance"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Get information about a VM instance resource within GCE. For more information see
[the official documentation](https://cloud.google.com/compute/docs/instances)
and
[API](https://cloud.google.com/compute/docs/reference/latest/instances).


## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const appserver = gcp.compute.getInstance({
    name: "primary-application-server",
    zone: "us-central1-a",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/d/datasource_compute_instance.html.markdown.





## Using GetInstance

{{< langchoose csharp nojavascript >}}


<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getInstance<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#GetInstanceArgs">GetInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#GetInstanceResult">GetInstanceResult</a></span>></span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_instance(</span>name=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, </span>zone=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#LookupInstanceArgs">LookupInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#LookupInstanceResult">LookupInstanceResult</a></span>, error)</span></code></pre></div>


<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetInstance </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceResult.html">GetInstanceResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceArgs.html">GetInstanceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>



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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance. One of `name` or `self_link` must be provided.
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
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
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
The self link of the instance. One of `name` or `self_link` must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone of the instance. If `self_link` is provided, this
value is ignored.  If neither `self_link` nor `zone` are provided, the
provider zone is used.
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
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance. One of `name` or `self_link` must be provided.
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
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
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
The self link of the instance. One of `name` or `self_link` must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone of the instance. If `self_link` is provided, this
value is ignored.  If neither `self_link` nor `zone` are provided, the
provider zone is used.
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
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance. One of `name` or `self_link` must be provided.
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
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
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
The self link of the instance. One of `name` or `self_link` must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone of the instance. If `self_link` is provided, this
value is ignored.  If neither `self_link` nor `zone` are provided, the
provider zone is used.
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
 (Optional)
The name of the instance. One of `name` or `self_link` must be provided.
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
If `self_link` is provided, this value is ignored.  If neither `self_link`
nor `project` are provided, the provider project is used.
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
The self link of the instance. One of `name` or `self_link` must be provided.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone of the instance. If `self_link` is provided, this
value is ignored.  If neither `self_link` nor `zone` are provided, the
provider zone is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## GetInstance Result

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
            <td class="align-top">Allow<wbr>Stopping<wbr>For<wbr>Update</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attached<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstanceattacheddisk">List&lt;Get<wbr>Instance<wbr>Attached<wbr>Disk&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} List of disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdisk">List&lt;Get<wbr>Instance<wbr>Boot<wbr>Disk&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The boot disk for the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Can<wbr>Ip<wbr>Forward</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether sending and receiving of packets with non-matching source or destination IPs is allowed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The CPU platform used by this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Current<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deletion<wbr>Protection</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether deletion protection is enabled on this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A brief description of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Desired<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Display</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Guest<wbr>Accelerators</td>
            <td class="align-top">
                
                <code><a href="#getinstanceguestaccelerator">List&lt;Get<wbr>Instance<wbr>Guest<wbr>Accelerator&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} List of the type and count of accelerator cards attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hostname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The server-assigned unique identifier of this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string></code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to create.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>Dictionary<string, string></code>
            </td>
            <td class="align-top">{{% md %}} Metadata key/value pairs made available within the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Startup<wbr>Script</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The minimum CPU platform specified for the VM instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterface">List&lt;Get<wbr>Instance<wbr>Network<wbr>Interface&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The networks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedulings</td>
            <td class="align-top">
                
                <code><a href="#getinstancescheduling">List&lt;Get<wbr>Instance<wbr>Scheduling&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The scheduling strategy being used by the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scratch<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancescratchdisk">List&lt;Get<wbr>Instance<wbr>Scratch<wbr>Disk&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The scratch disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code><a href="#getinstanceserviceaccount">List&lt;Get<wbr>Instance<wbr>Service<wbr>Account&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The service account to attach to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shielded<wbr>Instance<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstanceshieldedinstanceconfig">List&lt;Get<wbr>Instance<wbr>Shielded<wbr>Instance<wbr>Config&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The shielded vm config being used by the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The list of tags attached to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the tags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">Allow<wbr>Stopping<wbr>For<wbr>Update</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Attached<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstanceattacheddisk">[]Get<wbr>Instance<wbr>Attached<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} List of disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Boot<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdisk">[]Get<wbr>Instance<wbr>Boot<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} The boot disk for the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Can<wbr>Ip<wbr>Forward</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether sending and receiving of packets with non-matching source or destination IPs is allowed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The CPU platform used by this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Current<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deletion<wbr>Protection</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether deletion protection is enabled on this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A brief description of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Desired<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Display</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Guest<wbr>Accelerators</td>
            <td class="align-top">
                
                <code><a href="#getinstanceguestaccelerator">[]Get<wbr>Instance<wbr>Guest<wbr>Accelerator</a></code>
            </td>
            <td class="align-top">{{% md %}} List of the type and count of accelerator cards attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Hostname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The server-assigned unique identifier of this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to create.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Metadata key/value pairs made available within the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata<wbr>Startup<wbr>Script</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The minimum CPU platform specified for the VM instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterface">[]Get<wbr>Instance<wbr>Network<wbr>Interface</a></code>
            </td>
            <td class="align-top">{{% md %}} The networks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedulings</td>
            <td class="align-top">
                
                <code><a href="#getinstancescheduling">[]Get<wbr>Instance<wbr>Scheduling</a></code>
            </td>
            <td class="align-top">{{% md %}} The scheduling strategy being used by the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scratch<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancescratchdisk">[]Get<wbr>Instance<wbr>Scratch<wbr>Disk</a></code>
            </td>
            <td class="align-top">{{% md %}} The scratch disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Accounts</td>
            <td class="align-top">
                
                <code><a href="#getinstanceserviceaccount">[]Get<wbr>Instance<wbr>Service<wbr>Account</a></code>
            </td>
            <td class="align-top">{{% md %}} The service account to attach to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shielded<wbr>Instance<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstanceshieldedinstanceconfig">[]Get<wbr>Instance<wbr>Shielded<wbr>Instance<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The shielded vm config being used by the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The list of tags attached to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the tags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">allow<wbr>Stopping<wbr>For<wbr>Update</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attached<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstanceattacheddisk">Get<wbr>Instance<wbr>Attached<wbr>Disk[]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdisk">Get<wbr>Instance<wbr>Boot<wbr>Disk[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The boot disk for the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">can<wbr>Ip<wbr>Forward</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} Whether sending and receiving of packets with non-matching source or destination IPs is allowed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The CPU platform used by this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">current<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deletion<wbr>Protection</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} Whether deletion protection is enabled on this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A brief description of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">desired<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Display</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">guest<wbr>Accelerators</td>
            <td class="align-top">
                
                <code><a href="#getinstanceguestaccelerator">Get<wbr>Instance<wbr>Guest<wbr>Accelerator[]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of the type and count of accelerator cards attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hostname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The server-assigned unique identifier of this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to create.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>{[key: string]: string}</code>
            </td>
            <td class="align-top">{{% md %}} Metadata key/value pairs made available within the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata<wbr>Startup<wbr>Script</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The minimum CPU platform specified for the VM instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Interfaces</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterface">Get<wbr>Instance<wbr>Network<wbr>Interface[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The networks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedulings</td>
            <td class="align-top">
                
                <code><a href="#getinstancescheduling">Get<wbr>Instance<wbr>Scheduling[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The scheduling strategy being used by the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scratch<wbr>Disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancescratchdisk">Get<wbr>Instance<wbr>Scratch<wbr>Disk[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The scratch disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Accounts</td>
            <td class="align-top">
                
                <code><a href="#getinstanceserviceaccount">Get<wbr>Instance<wbr>Service<wbr>Account[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The service account to attach to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shielded<wbr>Instance<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstanceshieldedinstanceconfig">Get<wbr>Instance<wbr>Shielded<wbr>Instance<wbr>Config[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The shielded vm config being used by the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The list of tags attached to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the tags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">allow_<wbr>stopping_<wbr>for_<wbr>update</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">attached_<wbr>disks</td>
            <td class="align-top">
                
                <code><a href="#getinstanceattacheddisk">List[Get<wbr>Instance<wbr>Attached<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of disks attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">boot_<wbr>disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdisk">List[Get<wbr>Instance<wbr>Boot<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} The boot disk for the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">can_<wbr>ip_<wbr>forward</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether sending and receiving of packets with non-matching source or destination IPs is allowed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cpu_<wbr>platform</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The CPU platform used by this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">current_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deletion_<wbr>protection</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether deletion protection is enabled on this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A brief description of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">desired_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>display</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">guest_<wbr>accelerators</td>
            <td class="align-top">
                
                <code><a href="#getinstanceguestaccelerator">List[Get<wbr>Instance<wbr>Guest<wbr>Accelerator]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of the type and count of accelerator cards attached to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">hostname</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The server-assigned unique identifier of this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to create.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Metadata key/value pairs made available within the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata_<wbr>startup_<wbr>script</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>cpu_<wbr>platform</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The minimum CPU platform specified for the VM instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>interfaces</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterface">List[Get<wbr>Instance<wbr>Network<wbr>Interface]</a></code>
            </td>
            <td class="align-top">{{% md %}} The networks attached to the instance. Structure is documented below.
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
            <td class="align-top">schedulings</td>
            <td class="align-top">
                
                <code><a href="#getinstancescheduling">List[Get<wbr>Instance<wbr>Scheduling]</a></code>
            </td>
            <td class="align-top">{{% md %}} The scheduling strategy being used by the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scratch_<wbr>disks</td>
            <td class="align-top">
                
                <code><a href="#getinstancescratchdisk">List[Get<wbr>Instance<wbr>Scratch<wbr>Disk]</a></code>
            </td>
            <td class="align-top">{{% md %}} The scratch disks attached to the instance. Structure is documented below.
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
            <td class="align-top">service_<wbr>accounts</td>
            <td class="align-top">
                
                <code><a href="#getinstanceserviceaccount">List[Get<wbr>Instance<wbr>Service<wbr>Account]</a></code>
            </td>
            <td class="align-top">{{% md %}} The service account to attach to the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shielded_<wbr>instance_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#getinstanceshieldedinstanceconfig">List[Get<wbr>Instance<wbr>Shielded<wbr>Instance<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} The shielded vm config being used by the instance. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The list of tags attached to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique fingerprint of the tags.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Supporting Types

#### GetInstanceAttachedDisk
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceAttachedDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceAttachedDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceAttachedDisk.html">output</a> API doc for this type.
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
            <td class="align-top">Device<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
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
            <td class="align-top">Device<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
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
            <td class="align-top">device<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
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
            <td class="align-top">device_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceBootDisk
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceBootDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceBootDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceBootDisk.html">output</a> API doc for this type.
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
            <td class="align-top">Auto<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the disk will be auto-deleted when the instance is deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Device<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initialize<wbr>Params</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdiskinitializeparam">List&lt;Get<wbr>Instance<wbr>Boot<wbr>Disk<wbr>Initialize<wbr>Param<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters with which a disk was created alongside the instance.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
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
            <td class="align-top">Auto<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the disk will be auto-deleted when the instance is deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Device<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initialize<wbr>Params</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdiskinitializeparam">[]Get<wbr>Instance<wbr>Boot<wbr>Disk<wbr>Initialize<wbr>Param</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters with which a disk was created alongside the instance.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
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
            <td class="align-top">auto<wbr>Delete</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the disk will be auto-deleted when the instance is deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">device<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initialize<wbr>Params</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdiskinitializeparam">Get<wbr>Instance<wbr>Boot<wbr>Disk<wbr>Initialize<wbr>Param[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters with which a disk was created alongside the instance.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
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
            <td class="align-top">auto<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the disk will be auto-deleted when the instance is deleted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">device_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Name with which the attached disk is accessible
under `/dev/disk/by-id/`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Raw</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Encryption<wbr>Key<wbr>Sha256</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initialize<wbr>Params</td>
            <td class="align-top">
                
                <code><a href="#getinstancebootdiskinitializeparam">List[Get<wbr>Instance<wbr>Boot<wbr>Disk<wbr>Initialize<wbr>Param]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters with which a disk was created alongside the instance.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kms<wbr>Key<wbr>Self<wbr>Link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Read/write mode for the disk. One of `&#34;READ_ONLY&#34;` or `&#34;READ_WRITE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the disk attached to this instance.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceBootDiskInitializeParam
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceBootDiskInitializeParam">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceBootDiskInitializeParam">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceBootDiskInitializeParam.html">output</a> API doc for this type.
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
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The image from which this disk was initialised.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, object></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The size of the image in gigabytes.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
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
            <td class="align-top">Image</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The image from which this disk was initialised.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Size</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The size of the image in gigabytes.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
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
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The image from which this disk was initialised.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: any}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The size of the image in gigabytes.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
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
            <td class="align-top">image</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The image from which this disk was initialised.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A set of key/value label pairs assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">size</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The size of the image in gigabytes.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceGuestAccelerator
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceGuestAccelerator">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceGuestAccelerator">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceGuestAccelerator.html">output</a> API doc for this type.
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of the guest accelerator cards exposed to this instance.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of the guest accelerator cards exposed to this instance.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of the guest accelerator cards exposed to this instance.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The number of the guest accelerator cards exposed to this instance.
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
The accelerator type resource exposed to this instance. E.g. `nvidia-tesla-k80`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceNetworkInterface
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceNetworkInterface.html">output</a> API doc for this type.
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
            <td class="align-top">Access<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfaceaccessconfig">List&lt;Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Access<wbr>Config<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Access configurations, i.e. IPs via which this
instance can be accessed via the Internet. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Alias<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfacealiasiprange">List&lt;Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Alias<wbr>Ip<wbr>Range<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of alias IP ranges for this network interface. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the instance. One of `name` or `self_link` must be provided.
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
The name or self_link of the network attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The private IP address assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the subnetwork attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork<wbr>Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project in which the subnetwork belongs.
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
            <td class="align-top">Access<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfaceaccessconfig">[]Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Access<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Access configurations, i.e. IPs via which this
instance can be accessed via the Internet. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Alias<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfacealiasiprange">[]Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Alias<wbr>Ip<wbr>Range</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of alias IP ranges for this network interface. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the instance. One of `name` or `self_link` must be provided.
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
The name or self_link of the network attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The private IP address assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the subnetwork attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork<wbr>Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project in which the subnetwork belongs.
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
            <td class="align-top">access<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfaceaccessconfig">Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Access<wbr>Config[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Access configurations, i.e. IPs via which this
instance can be accessed via the Internet. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">alias<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfacealiasiprange">Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Alias<wbr>Ip<wbr>Range[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of alias IP ranges for this network interface. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the instance. One of `name` or `self_link` must be provided.
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
The name or self_link of the network attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The private IP address assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the subnetwork attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork<wbr>Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project in which the subnetwork belongs.
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
            <td class="align-top">access<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfaceaccessconfig">List[Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Access<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Access configurations, i.e. IPs via which this
instance can be accessed via the Internet. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">alias<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code><a href="#getinstancenetworkinterfacealiasiprange">List[Get<wbr>Instance<wbr>Network<wbr>Interface<wbr>Alias<wbr>Ip<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of alias IP ranges for this network interface. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the instance. One of `name` or `self_link` must be provided.
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
The name or self_link of the network attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The private IP address assigned to the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name or self_link of the subnetwork attached to this interface.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork<wbr>Project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project in which the subnetwork belongs.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceNetworkInterfaceAccessConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceNetworkInterfaceAccessConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceNetworkInterfaceAccessConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceNetworkInterfaceAccessConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Nat<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The IP address that is be 1:1 mapped to the instance&#39;s
network ip.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [networking tier][network-tier] used for configuring this instance. One of `PREMIUM` or `STANDARD`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ptr<wbr>Domain<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS domain name for the public PTR record.
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
            <td class="align-top">Nat<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The IP address that is be 1:1 mapped to the instance&#39;s
network ip.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [networking tier][network-tier] used for configuring this instance. One of `PREMIUM` or `STANDARD`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ptr<wbr>Domain<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS domain name for the public PTR record.
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
            <td class="align-top">nat<wbr>Ip</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The IP address that is be 1:1 mapped to the instance&#39;s
network ip.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Tier</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [networking tier][network-tier] used for configuring this instance. One of `PREMIUM` or `STANDARD`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Ptr<wbr>Domain<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS domain name for the public PTR record.
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
            <td class="align-top">nat<wbr>Ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The IP address that is be 1:1 mapped to the instance&#39;s
network ip.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [networking tier][network-tier] used for configuring this instance. One of `PREMIUM` or `STANDARD`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Ptr<wbr>Domain<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The DNS domain name for the public PTR record.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceNetworkInterfaceAliasIpRange
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceNetworkInterfaceAliasIpRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceNetworkInterfaceAliasIpRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceNetworkInterfaceAliasIpRange.html">output</a> API doc for this type.
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
The IP CIDR range represented by this alias IP range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The subnetwork secondary range name specifying
the secondary range from which to allocate the IP CIDR range for this alias IP
range.
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
The IP CIDR range represented by this alias IP range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The subnetwork secondary range name specifying
the secondary range from which to allocate the IP CIDR range for this alias IP
range.
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
The IP CIDR range represented by this alias IP range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The subnetwork secondary range name specifying
the secondary range from which to allocate the IP CIDR range for this alias IP
range.
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
The IP CIDR range represented by this alias IP range.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The subnetwork secondary range name specifying
the secondary range from which to allocate the IP CIDR range for this alias IP
range.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceScheduling
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceScheduling">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceScheduling">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceScheduling.html">output</a> API doc for this type.
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
            <td class="align-top">Automatic<wbr>Restart</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies if the instance should be
restarted if it was terminated by Compute Engine (not a user).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Affinities</td>
            <td class="align-top">
                
                <code><a href="#getinstanceschedulingnodeaffinity">List&lt;Get<wbr>Instance<wbr>Scheduling<wbr>Node<wbr>Affinity<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Host<wbr>Maintenance</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Describes maintenance behavior for the
instance. One of `MIGRATE` or `TERMINATE`, for more info, read
[here](https://cloud.google.com/compute/docs/instances/setting-instance-scheduling-options)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preemptible</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the instance is preemptible.
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
            <td class="align-top">Automatic<wbr>Restart</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies if the instance should be
restarted if it was terminated by Compute Engine (not a user).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Affinities</td>
            <td class="align-top">
                
                <code><a href="#getinstanceschedulingnodeaffinity">[]Get<wbr>Instance<wbr>Scheduling<wbr>Node<wbr>Affinity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Host<wbr>Maintenance</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Describes maintenance behavior for the
instance. One of `MIGRATE` or `TERMINATE`, for more info, read
[here](https://cloud.google.com/compute/docs/instances/setting-instance-scheduling-options)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preemptible</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the instance is preemptible.
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
            <td class="align-top">automatic<wbr>Restart</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies if the instance should be
restarted if it was terminated by Compute Engine (not a user).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Affinities</td>
            <td class="align-top">
                
                <code><a href="#getinstanceschedulingnodeaffinity">Get<wbr>Instance<wbr>Scheduling<wbr>Node<wbr>Affinity[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on<wbr>Host<wbr>Maintenance</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Describes maintenance behavior for the
instance. One of `MIGRATE` or `TERMINATE`, for more info, read
[here](https://cloud.google.com/compute/docs/instances/setting-instance-scheduling-options)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preemptible</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the instance is preemptible.
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
            <td class="align-top">automatic<wbr>Restart</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies if the instance should be
restarted if it was terminated by Compute Engine (not a user).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Affinities</td>
            <td class="align-top">
                
                <code><a href="#getinstanceschedulingnodeaffinity">List[Get<wbr>Instance<wbr>Scheduling<wbr>Node<wbr>Affinity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on<wbr>Host<wbr>Maintenance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Describes maintenance behavior for the
instance. One of `MIGRATE` or `TERMINATE`, for more info, read
[here](https://cloud.google.com/compute/docs/instances/setting-instance-scheduling-options)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preemptible</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Whether the instance is preemptible.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceSchedulingNodeAffinity
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceSchedulingNodeAffinity">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceSchedulingNodeAffinity">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceSchedulingNodeAffinity.html">output</a> API doc for this type.
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
            <td class="align-top">Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Operator</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Values</td>
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
            <td class="align-top">Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Operator</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Values</td>
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
            <td class="align-top">key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">operator</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">values</td>
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
            <td class="align-top">key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">operator</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">values</td>
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





#### GetInstanceScratchDisk
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceScratchDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceScratchDisk">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceScratchDisk.html">output</a> API doc for this type.
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
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The disk interface used for attaching this disk. One of `SCSI` or `NVME`.
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
            <td class="align-top">Interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The disk interface used for attaching this disk. One of `SCSI` or `NVME`.
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
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The disk interface used for attaching this disk. One of `SCSI` or `NVME`.
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
            <td class="align-top">interface</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The disk interface used for attaching this disk. One of `SCSI` or `NVME`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceServiceAccount
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceServiceAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceServiceAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceServiceAccount.html">output</a> API doc for this type.
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
            <td class="align-top">Email</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The service account e-mail address.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scopes</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of service scopes.
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
            <td class="align-top">Email</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The service account e-mail address.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scopes</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of service scopes.
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
            <td class="align-top">email</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The service account e-mail address.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scopes</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of service scopes.
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
            <td class="align-top">email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The service account e-mail address.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scopes</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of service scopes.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetInstanceShieldedInstanceConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetInstanceShieldedInstanceConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#GetInstanceShieldedInstanceConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.GetInstanceShieldedInstanceConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Vtpm</td>
            <td class="align-top">
                
                <code>bool</code>
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
            <td class="align-top">Enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Vtpm</td>
            <td class="align-top">
                
                <code>bool</code>
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
            <td class="align-top">enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Vtpm</td>
            <td class="align-top">
                
                <code>boolean</code>
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
            <td class="align-top">enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Vtpm</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








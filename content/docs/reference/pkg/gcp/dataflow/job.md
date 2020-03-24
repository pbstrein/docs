
---
title: "Job"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Creates a job on Dataflow, which is an implementation of Apache Beam running on Google Compute Engine. For more information see
the official documentation for
[Beam](https://beam.apache.org) and [Dataflow](https://cloud.google.com/dataflow/).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const bigDataJob = new gcp.dataflow.Job("big_data_job", {
    parameters: {
        baz: "qux",
        foo: "bar",
    },
    tempGcsLocation: "gs://my-bucket/tmp_dir",
    templateGcsPath: "gs://my-bucket/templates/template_file",
});
```

## Note on "destroy" / "apply"

There are many types of Dataflow jobs.  Some Dataflow jobs run constantly, getting new data from (e.g.) a GCS bucket, and outputting data continuously.  Some jobs process a set amount of data then terminate.  All jobs can fail while running due to programming errors or other issues.  In this way, Dataflow jobs are different from most other Google resources.

The Dataflow resource is considered 'existing' while it is in a nonterminal state.  If it reaches a terminal state (e.g. 'FAILED', 'COMPLETE', 'CANCELLED'), it will be recreated on the next 'apply'.  This is as expected for jobs which run continuously, but may surprise users who use this resource for other kinds of Dataflow jobs.

A Dataflow job which is 'destroyed' may be "cancelled" or "drained".  If "cancelled", the job terminates - any data written remains where it is, but no new data will be processed.  If "drained", no new data will enter the pipeline, but any data currently in the pipeline will finish being processed.  The default is "cancelled", but if a user sets `on_delete` to `"drain"` in the configuration, you may experience a long wait for your `pulumi destroy` to complete.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/dataflow_job.html.markdown.



## Create a Job Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataflow/#Job">Job</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataflow/#JobArgs">JobArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Job</span><span class="p">(resource_name, opts=None, </span>ip_configuration=None<span class="p">, </span>labels=None<span class="p">, </span>machine_type=None<span class="p">, </span>max_workers=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>on_delete=None<span class="p">, </span>parameters=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>service_account_email=None<span class="p">, </span>subnetwork=None<span class="p">, </span>temp_gcs_location=None<span class="p">, </span>template_gcs_path=None<span class="p">, </span>zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewJob<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataflow?tab=doc#JobArgs">JobArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataflow?tab=doc#Job">Job</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataflow.Job.html">Job</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataflow.JobArgs.html">JobArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Job resource with the given unique name, arguments, and options.

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
            <td class="align-top">Ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, object>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Workers</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Delete</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parameters</td>
            <td class="align-top">
                
                <code>Dictionary<string, object>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The GCS path to the Dataflow job template.
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">Ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Workers</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Delete</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parameters</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The GCS path to the Dataflow job template.
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: any}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Workers</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on<wbr>Delete</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parameters</td>
            <td class="align-top">
                
                <code>{[key: string]: any}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The GCS path to the Dataflow job template.
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">ip_<wbr>configuration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>workers</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on_<wbr>delete</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parameters</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>account_<wbr>email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">temp_<wbr>gcs_<wbr>location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">template_<wbr>gcs_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The GCS path to the Dataflow job template.
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Job Output Properties

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
            <td class="align-top">Ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Job<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, object>?</code>
            </td>
            <td class="align-top">{{% md %}} User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Workers</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by Dataflow.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Delete</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parameters</td>
            <td class="align-top">
                
                <code>Dictionary<string, object>?</code>
            </td>
            <td class="align-top">{{% md %}} Key/Value pairs to be passed to the Dataflow job (as used in the template).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS path to the Dataflow job template.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">Ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Job<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Workers</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by Dataflow.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Delete</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parameters</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} Key/Value pairs to be passed to the Dataflow job (as used in the template).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">State</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS path to the Dataflow job template.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zone</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">job<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: any}?</code>
            </td>
            <td class="align-top">{{% md %}} User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Workers</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by Dataflow.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on<wbr>Delete</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parameters</td>
            <td class="align-top">
                
                <code>{[key: string]: any}?</code>
            </td>
            <td class="align-top">{{% md %}} Key/Value pairs to be passed to the Dataflow job (as used in the template).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS path to the Dataflow job template.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">ip_<wbr>configuration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">job_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>workers</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A unique name for the resource, required by Dataflow.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on_<wbr>delete</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parameters</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} Key/Value pairs to be passed to the Dataflow job (as used in the template).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The project in which the resource belongs. If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>account_<wbr>email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Service Account email used to create the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">state</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">temp_<wbr>gcs_<wbr>location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">template_<wbr>gcs_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The GCS path to the Dataflow job template.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zone</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The zone in which the created job should run. If it is not provided, the provider zone is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Job Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataflow/#JobState">JobState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataflow/#Job">Job</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>ip_configuration=None<span class="p">, </span>job_id=None<span class="p">, </span>labels=None<span class="p">, </span>machine_type=None<span class="p">, </span>max_workers=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>on_delete=None<span class="p">, </span>parameters=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>service_account_email=None<span class="p">, </span>state=None<span class="p">, </span>subnetwork=None<span class="p">, </span>temp_gcs_location=None<span class="p">, </span>template_gcs_path=None<span class="p">, </span>type=None<span class="p">, </span>zone=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetJob<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataflow?tab=doc#JobState">JobState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataflow?tab=doc#Job">Job</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataflow.Job.html">Job</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataflow.JobState.html">JobState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Job resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Job<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, object>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Workers</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Delete</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parameters</td>
            <td class="align-top">
                
                <code>Dictionary<string, object>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
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
The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS path to the Dataflow job template.
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
The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">Ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Job<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Machine<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Workers</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">On<wbr>Delete</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parameters</td>
            <td class="align-top">
                
                <code>map[string]interface{}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
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
The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS path to the Dataflow job template.
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
The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">ip<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">job<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: any}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Workers</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on<wbr>Delete</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parameters</td>
            <td class="align-top">
                
                <code>{[key: string]: any}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Account<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
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
The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">temp<wbr>Gcs<wbr>Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">template<wbr>Gcs<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS path to the Dataflow job template.
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
The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
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
            <td class="align-top">ip_<wbr>configuration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for VM IPs.  Options are `&#34;WORKER_IP_PUBLIC&#34;` or `&#34;WORKER_IP_PRIVATE&#34;`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">job_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique ID of this job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
User labels to be specified for the job. Keys and values should follow the restrictions
specified in the [labeling restrictions](https://cloud.google.com/compute/docs/labeling-resources#restrictions) page.
**NOTE**: Google-provided Dataflow templates often provide default labels that begin with `goog-dataflow-provided`.
Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">machine_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The machine type to use for the job.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>workers</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of workers permitted to work on the job.  More workers may improve processing speed at additional cost.
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
A unique name for the resource, required by Dataflow.
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
The network to which VMs will be assigned. If it is not provided, &#34;default&#34; will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">on_<wbr>delete</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One of &#34;drain&#34; or &#34;cancel&#34;.  Specifies behavior of deletion during `pulumi destroy`.  See above note.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parameters</td>
            <td class="align-top">
                
                <code>Dict[str, Any]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key/Value pairs to be passed to the Dataflow job (as used in the template).
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
The project in which the resource belongs. If it is not provided, the provider project is used.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>account_<wbr>email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Service Account email used to create the job.
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
The current state of the resource, selected from the [JobState enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobState)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The subnetwork to which VMs will be assigned. Should be of the form &#34;regions/REGION/subnetworks/SUBNETWORK&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">temp_<wbr>gcs_<wbr>location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A writeable location on GCS for the Dataflow job to dump its temporary data.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">template_<wbr>gcs_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS path to the Dataflow job template.
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
The type of this job, selected from the [JobType enum](https://cloud.google.com/dataflow/docs/reference/rest/v1b3/projects.jobs#Job.JobType)
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
The zone in which the created job should run. If it is not provided, the provider zone is used.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










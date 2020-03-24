
---
title: "BackendBucket"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Backend buckets allow you to use Google Cloud Storage buckets with HTTP(S)
load balancing.

An HTTP(S) load balancer can direct traffic to specified URLs to a
backend bucket rather than a backend service. It can send requests for
static content to a Cloud Storage bucket and requests for dynamic content
to a virtual machine instance.


To get more information about BackendBucket, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/v1/backendBuckets)
* How-to Guides
    * [Using a Cloud Storage bucket as a load balancer backend](https://cloud.google.com/compute/docs/load-balancing/http/backend-bucket)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_backend_bucket.html.markdown.



## Create a BackendBucket Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendBucket">BackendBucket</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendBucketArgs">BackendBucketArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BackendBucket</span><span class="p">(resource_name, opts=None, </span>bucket_name=None<span class="p">, </span>cdn_policy=None<span class="p">, </span>description=None<span class="p">, </span>enable_cdn=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBackendBucket<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendBucketArgs">BackendBucketArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendBucket">BackendBucket</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendBucket.html">BackendBucket</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendBucketArgs.html">BackendBucketArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a BackendBucket resource with the given unique name, arguments, and options.

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
            <td class="align-top">Bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">Bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">*Backend<wbr>Bucket<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">bucket_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Dict[Backend<wbr>Bucket<wbr>Cdn<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>cdn</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
    
    </tbody>
</table>


{{% /lang %}}







## BackendBucket Output Properties

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
            <td class="align-top">Bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">Bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">bucket_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Dict[Backend<wbr>Bucket<wbr>Cdn<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>cdn</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendBucket.
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








## Look up an Existing BackendBucket Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendBucketState">BackendBucketState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendBucket">BackendBucket</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket_name=None<span class="p">, </span>cdn_policy=None<span class="p">, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>enable_cdn=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBackendBucket<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendBucketState">BackendBucketState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendBucket">BackendBucket</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendBucket.html">BackendBucket</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendBucketState.html">BackendBucketState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing BackendBucket resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">Bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">*Backend<wbr>Bucket<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">bucket<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Backend<wbr>Bucket<wbr>Cdn<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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
            <td class="align-top">bucket_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud Storage bucket name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#backendbucketcdnpolicy">Dict[Backend<wbr>Bucket<wbr>Cdn<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this Backend Bucket.
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An optional textual description of the resource; provided by the client when the resource is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>cdn</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, enable Cloud CDN for this BackendBucket.
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

#### BackendBucketCdnPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendBucketCdnPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendBucketCdnPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendBucketCdnPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendBucketCdnPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendBucketCdnPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendBucketCdnPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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
            <td class="align-top">Signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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
            <td class="align-top">signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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
            <td class="align-top">signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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








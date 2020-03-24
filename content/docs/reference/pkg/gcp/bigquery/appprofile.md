
---
title: "AppProfile"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

App profile is a configuration object describing how Cloud Bigtable should treat traffic from a particular end user application.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/bigtable_app_profile.html.markdown.



## Create a AppProfile Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#AppProfile">AppProfile</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#AppProfileArgs">AppProfileArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AppProfile</span><span class="p">(resource_name, opts=None, </span>app_profile_id=None<span class="p">, </span>description=None<span class="p">, </span>ignore_warnings=None<span class="p">, </span>instance=None<span class="p">, </span>multi_cluster_routing_use_any=None<span class="p">, </span>project=None<span class="p">, </span>single_cluster_routing=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAppProfile<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#AppProfileArgs">AppProfileArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#AppProfile">AppProfile</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.AppProfile.html">AppProfile</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.AppProfileArgs.html">AppProfileArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a AppProfile resource with the given unique name, arguments, and options.

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
            <td class="align-top">App<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
            <td class="align-top">Single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
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
            <td class="align-top">App<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
            <td class="align-top">Single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">*App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
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
            <td class="align-top">app<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
            <td class="align-top">single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
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
            <td class="align-top">app_<wbr>profile_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore_<wbr>warnings</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">multi_<wbr>cluster_<wbr>routing_<wbr>use_<wbr>any</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
            <td class="align-top">single_<wbr>cluster_<wbr>routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">Dict[App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## AppProfile Output Properties

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
            <td class="align-top">App<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">Single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing?</a></code>
            </td>
            <td class="align-top">{{% md %}} Use a single-cluster routing policy.
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
            <td class="align-top">App<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">Single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">*App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing</a></code>
            </td>
            <td class="align-top">{{% md %}} Use a single-cluster routing policy.
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
            <td class="align-top">app<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing?</a></code>
            </td>
            <td class="align-top">{{% md %}} Use a single-cluster routing policy.
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
            <td class="align-top">app_<wbr>profile_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore_<wbr>warnings</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">multi_<wbr>cluster_<wbr>routing_<wbr>use_<wbr>any</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">single_<wbr>cluster_<wbr>routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">Dict[App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing]</a></code>
            </td>
            <td class="align-top">{{% md %}} Use a single-cluster routing policy.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing AppProfile Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#AppProfileState">AppProfileState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#AppProfile">AppProfile</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_profile_id=None<span class="p">, </span>description=None<span class="p">, </span>ignore_warnings=None<span class="p">, </span>instance=None<span class="p">, </span>multi_cluster_routing_use_any=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>single_cluster_routing=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAppProfile<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#AppProfileState">AppProfileState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#AppProfile">AppProfile</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.AppProfile.html">AppProfile</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.AppProfileState.html">AppProfileState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing AppProfile resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">App<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">Single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
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
            <td class="align-top">App<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">Single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">*App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
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
            <td class="align-top">app<wbr>Profile<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore<wbr>Warnings</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">multi<wbr>Cluster<wbr>Routing<wbr>Use<wbr>Any</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">single<wbr>Cluster<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
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
            <td class="align-top">app_<wbr>profile_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique name of the app profile in the form &#39;[_a-zA-Z0-9][-_.a-zA-Z0-9]*&#39;.
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
Long form description of the use case for this app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore_<wbr>warnings</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, ignore safety checks when deleting/updating the app profile.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the instance to create the app profile within.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">multi_<wbr>cluster_<wbr>routing_<wbr>use_<wbr>any</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, read/write requests are routed to the nearest cluster in the instance, and will fail over to the nearest
cluster that is available in the event of transient errors or delays. Clusters in a region are considered equidistant.
Choosing this option sacrifices read-your-writes consistency to improve availability.
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
The unique name of the requested app profile. Values are of the form
&#39;projects/&lt;project&gt;/instances/&lt;instance&gt;/appProfiles/&lt;appProfileId&gt;&#39;.
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
            <td class="align-top">single_<wbr>cluster_<wbr>routing</td>
            <td class="align-top">
                
                <code><a href="#appprofilesingleclusterrouting">Dict[App<wbr>Profile<wbr>Single<wbr>Cluster<wbr>Routing]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Use a single-cluster routing policy.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### AppProfileSingleClusterRouting
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AppProfileSingleClusterRouting">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AppProfileSingleClusterRouting">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#AppProfileSingleClusterRoutingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#AppProfileSingleClusterRoutingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.AppProfileSingleClusterRoutingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.AppProfileSingleClusterRouting.html">output</a> API doc for this type.
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
            <td class="align-top">Allow<wbr>Transactional<wbr>Writes</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Id</td>
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
            <td class="align-top">Allow<wbr>Transactional<wbr>Writes</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Id</td>
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
            <td class="align-top">allow<wbr>Transactional<wbr>Writes</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Id</td>
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
            <td class="align-top">allow<wbr>Transactional<wbr>Writes</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>id</td>
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








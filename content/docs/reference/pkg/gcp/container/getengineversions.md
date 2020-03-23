
---
title: "GetEngineVersions"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

## a---

subcategory: "Kubernetes (Container) Engine"
layout: "google"
page_title: "Google: gcp.container.getEngineVersions"
sidebar_current: "docs-google-datasource-container-versions"
description: |-
  Provides lists of available Google Kubernetes Engine versions for masters and nodes.
---

# google\_container\_engine\_versions

Provides access to available Google Kubernetes Engine versions in a zone or region for a given project.

> If you are using the `gcp.container.getEngineVersions` datasource with a
regional cluster, ensure that you have provided a region as the `location` to
the datasource. A region can have a different set of supported versions than
its component zones, and not all zones in a region are guaranteed to
support the same version.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/d/google_container_engine_versions.html.markdown.





## Using GetEngineVersions

{{< langchoose csharp nojavascript >}}


<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getEngineVersions<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#GetEngineVersionsArgs">GetEngineVersionsArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#GetEngineVersionsResult">GetEngineVersionsResult</a></span>></span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_engine_versions(</span>location=None<span class="p">, </span>project=None<span class="p">, </span>version_prefix=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupEngineVersions<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#LookupEngineVersionsArgs">LookupEngineVersionsArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#LookupEngineVersionsResult">LookupEngineVersionsResult</a></span>, error)</span></code></pre></div>


<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetEngineVersions </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.GetEngineVersionsResult.html">GetEngineVersionsResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.GetEngineVersionsArgs.html">GetEngineVersionsArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
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
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) to list versions for.
Must exactly match the location the cluster will be deployed in, or listed
versions may not be available. If `location`, `region`, and `zone` are not
specified, the provider-level zone must be set and is used instead.
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
ID of the project to list available cluster versions for. Should match the project the cluster will be deployed to.
Defaults to the project that the provider is authenticated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If provided, this provider will only return versions
that match the string prefix. For example, `1.11.` will match all `1.11` series
releases. Since this is just a string match, it&#39;s recommended that you append a
`.` after minor versions to ensure that prefixes such as `1.1` don&#39;t match
versions like `1.12.5-gke.10` accidentally. See [the docs on versioning schema](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#versioning_scheme)
for full details on how version strings are formatted.
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
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) to list versions for.
Must exactly match the location the cluster will be deployed in, or listed
versions may not be available. If `location`, `region`, and `zone` are not
specified, the provider-level zone must be set and is used instead.
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
ID of the project to list available cluster versions for. Should match the project the cluster will be deployed to.
Defaults to the project that the provider is authenticated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If provided, this provider will only return versions
that match the string prefix. For example, `1.11.` will match all `1.11` series
releases. Since this is just a string match, it&#39;s recommended that you append a
`.` after minor versions to ensure that prefixes such as `1.1` don&#39;t match
versions like `1.12.5-gke.10` accidentally. See [the docs on versioning schema](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#versioning_scheme)
for full details on how version strings are formatted.
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
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) to list versions for.
Must exactly match the location the cluster will be deployed in, or listed
versions may not be available. If `location`, `region`, and `zone` are not
specified, the provider-level zone must be set and is used instead.
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
ID of the project to list available cluster versions for. Should match the project the cluster will be deployed to.
Defaults to the project that the provider is authenticated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If provided, this provider will only return versions
that match the string prefix. For example, `1.11.` will match all `1.11` series
releases. Since this is just a string match, it&#39;s recommended that you append a
`.` after minor versions to ensure that prefixes such as `1.1` don&#39;t match
versions like `1.12.5-gke.10` accidentally. See [the docs on versioning schema](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#versioning_scheme)
for full details on how version strings are formatted.
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
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) to list versions for.
Must exactly match the location the cluster will be deployed in, or listed
versions may not be available. If `location`, `region`, and `zone` are not
specified, the provider-level zone must be set and is used instead.
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
ID of the project to list available cluster versions for. Should match the project the cluster will be deployed to.
Defaults to the project that the provider is authenticated with.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If provided, this provider will only return versions
that match the string prefix. For example, `1.11.` will match all `1.11` series
releases. Since this is just a string match, it&#39;s recommended that you append a
`.` after minor versions to ensure that prefixes such as `1.1` don&#39;t match
versions like `1.12.5-gke.10` accidentally. See [the docs on versioning schema](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#versioning_scheme)
for full details on how version strings are formatted.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## GetEngineVersions Result

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
            <td class="align-top">Default<wbr>Cluster<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes the service deploys by default.
 {{% /md %}}

            
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
            <td class="align-top">Latest<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Latest<wbr>Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">Valid<wbr>Master<wbr>Versions</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Valid<wbr>Node<wbr>Versions</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Prefix</td>
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
            <td class="align-top">Default<wbr>Cluster<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes the service deploys by default.
 {{% /md %}}

            
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
            <td class="align-top">Latest<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Latest<wbr>Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">Valid<wbr>Master<wbr>Versions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Valid<wbr>Node<wbr>Versions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Prefix</td>
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
            <td class="align-top">default<wbr>Cluster<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes the service deploys by default.
 {{% /md %}}

            
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
            <td class="align-top">latest<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">latest<wbr>Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">valid<wbr>Master<wbr>Versions</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">valid<wbr>Node<wbr>Versions</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Prefix</td>
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
            <td class="align-top">default_<wbr>cluster_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes the service deploys by default.
 {{% /md %}}

            
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
            <td class="align-top">latest_<wbr>master_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">latest_<wbr>node_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The latest version available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
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
            <td class="align-top">valid_<wbr>master_<wbr>versions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with master instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">valid_<wbr>node_<wbr>versions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of versions available in the given zone for use with node instances.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








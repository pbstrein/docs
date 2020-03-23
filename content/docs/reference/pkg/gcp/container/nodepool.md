
---
title: "NodePool"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a node pool in a Google Kubernetes Engine (GKE) cluster separately from
the cluster control plane. For more information see [the official documentation](https://cloud.google.com/container-engine/docs/node-pools)
and [the API reference](https://cloud.google.com/container-engine/reference/rest/v1/projects.zones.clusters.nodePools).

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/container_node_pool.html.markdown.



## Create a NodePool Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#NodePool">NodePool</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#NodePoolArgs">NodePoolArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NodePool</span><span class="p">(resource_name, opts=None, </span>autoscaling=None<span class="p">, </span>cluster=None<span class="p">, </span>initial_node_count=None<span class="p">, </span>location=None<span class="p">, </span>management=None<span class="p">, </span>max_pods_per_node=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>node_config=None<span class="p">, </span>node_count=None<span class="p">, </span>node_locations=None<span class="p">, </span>project=None<span class="p">, </span>upgrade_settings=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNodePool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolArgs">NodePoolArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePool">NodePool</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePool.html">NodePool</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolArgs.html">NodePoolArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a NodePool resource with the given unique name, arguments, and options.

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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Node<wbr>Pool<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Node<wbr>Pool<wbr>Upgrade<wbr>Settings<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">*Node<wbr>Pool<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">*Node<wbr>Pool<wbr>Management</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">*Node<wbr>Pool<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">*Node<wbr>Pool<wbr>Upgrade<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Node<wbr>Pool<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Locations</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Node<wbr>Pool<wbr>Upgrade<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Dict[Node<wbr>Pool<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial_<wbr>node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Dict[Node<wbr>Pool<wbr>Management]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>pods_<wbr>per_<wbr>node</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Dict[Node<wbr>Pool<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>locations</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Dict[Node<wbr>Pool<wbr>Upgrade<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## NodePool Output Properties

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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Node<wbr>Pool<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management</a></code>
            </td>
            <td class="align-top">{{% md %}} Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} )
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Node<wbr>Pool<wbr>Upgrade<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">*Node<wbr>Pool<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management</a></code>
            </td>
            <td class="align-top">{{% md %}} Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} )
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">*Node<wbr>Pool<wbr>Upgrade<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Node<wbr>Pool<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management</a></code>
            </td>
            <td class="align-top">{{% md %}} Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Count</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Locations</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} )
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Node<wbr>Pool<wbr>Upgrade<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Dict[Node<wbr>Pool<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial_<wbr>node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>group_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Dict[Node<wbr>Pool<wbr>Management]</a></code>
            </td>
            <td class="align-top">{{% md %}} Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>pods_<wbr>per_<wbr>node</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Dict[Node<wbr>Pool<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>locations</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} )
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Dict[Node<wbr>Pool<wbr>Upgrade<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing NodePool Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#NodePoolState">NodePoolState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#NodePool">NodePool</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>autoscaling=None<span class="p">, </span>cluster=None<span class="p">, </span>initial_node_count=None<span class="p">, </span>instance_group_urls=None<span class="p">, </span>location=None<span class="p">, </span>management=None<span class="p">, </span>max_pods_per_node=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>node_config=None<span class="p">, </span>node_count=None<span class="p">, </span>node_locations=None<span class="p">, </span>project=None<span class="p">, </span>upgrade_settings=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNodePool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolState">NodePoolState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePool">NodePool</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePool.html">NodePool</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolState.html">NodePoolState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing NodePool resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Node<wbr>Pool<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Node<wbr>Pool<wbr>Upgrade<wbr>Settings<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">*Node<wbr>Pool<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">*Node<wbr>Pool<wbr>Management</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">*Node<wbr>Pool<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">*Node<wbr>Pool<wbr>Upgrade<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Node<wbr>Pool<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Node<wbr>Pool<wbr>Management?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Node<wbr>Pool<wbr>Node<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Locations</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Node<wbr>Pool<wbr>Upgrade<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
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
            <td class="align-top">autoscaling</td>
            <td class="align-top">
                
                <code><a href="#nodepoolautoscaling">Dict[Node<wbr>Pool<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration required by cluster autoscaler to adjust
the size of the node pool to the current cluster usage. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The cluster to create the node pool for. Cluster must be present in `location` provided for zonal clusters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial_<wbr>node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The initial number of nodes for the pool. In
regional or multi-zonal clusters, this is the number of nodes per zone. Changing
this will force recreation of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>group_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The resource URLs of the managed instance groups associated with this node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location (region or zone) of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#nodepoolmanagement">Dict[Node<wbr>Pool<wbr>Management]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Node management configuration, wherein auto-repair and
auto-upgrade is configured. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>pods_<wbr>per_<wbr>node</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum number of pods per node in this node pool.
Note that this does not work on node pools which are &#34;route-based&#34; - that is, node
pools belonging to clusters that do not have IP Aliasing enabled.
See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
The name of the node pool. If left blank, this provider will
auto-generate a unique name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Creates a unique name for the node pool beginning
with the specified prefix. Conflicts with `name`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfig">Dict[Node<wbr>Pool<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The node configuration of the pool. See
gcp.container.Cluster for schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of nodes per instance group. This field can be used to
update the number of nodes per instance group but should not be used alongside `autoscaling`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>locations</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
)
The list of zones in which the node pool&#39;s nodes should be located. Nodes must
be in the region of their regional cluster or in the same region as their
cluster&#39;s zone for zonal clusters. If unspecified, the cluster-level
`node_locations` will be used.
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
The ID of the project in which to create the node pool. If blank,
the provider-configured project will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#nodepoolupgradesettings">Dict[Node<wbr>Pool<wbr>Upgrade<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version for the nodes in this pool. Note that if this field
and `auto_upgrade` are both specified, they will fight each other for what the node version should
be, so setting both is highly discouraged. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as this provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### NodePoolAutoscaling
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolAutoscaling">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolAutoscaling">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolAutoscalingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolAutoscalingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolAutoscalingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolAutoscaling.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Node<wbr>Count</td>
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
            <td class="align-top">Max<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Node<wbr>Count</td>
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
            <td class="align-top">max<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Node<wbr>Count</td>
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
            <td class="align-top">max<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Node<wbr>Count</td>
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





#### NodePoolManagement
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolManagement">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolManagement">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolManagementArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolManagementOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolManagementArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolManagement.html">output</a> API doc for this type.
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
            <td class="align-top">Auto<wbr>Repair</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Auto<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>bool?</code>
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
            <td class="align-top">Auto<wbr>Repair</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Auto<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>*bool</code>
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
            <td class="align-top">auto<wbr>Repair</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">auto<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>boolean?</code>
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
            <td class="align-top">auto<wbr>Repair</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">auto<wbr>Upgrade</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### NodePoolNodeConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolNodeConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolNodeConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Boot<wbr>Disk<wbr>Kms<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Guest<wbr>Accelerators</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigguestaccelerator">List&lt;Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Ssd<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth<wbr>Scopes</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preemptible</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sandbox<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigsandboxconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shielded<wbr>Instance<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigshieldedinstanceconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Taints</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigtaint">List&lt;Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigworkloadmetadataconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config<wbr>Args?</a></code>
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
            <td class="align-top">Boot<wbr>Disk<wbr>Kms<wbr>Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disk<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Guest<wbr>Accelerators</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigguestaccelerator">[]Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Image<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Local<wbr>Ssd<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metadata</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth<wbr>Scopes</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preemptible</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sandbox<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigsandboxconfig">*Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Account</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Shielded<wbr>Instance<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigshieldedinstanceconfig">*Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Taints</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigtaint">[]Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigworkloadmetadataconfig">*Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config</a></code>
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
            <td class="align-top">boot<wbr>Disk<wbr>Kms<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">guest<wbr>Accelerators</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigguestaccelerator">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local<wbr>Ssd<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Cpu<wbr>Platform</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth<wbr>Scopes</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preemptible</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sandbox<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigsandboxconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shielded<wbr>Instance<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigshieldedinstanceconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">taints</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigtaint">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigworkloadmetadataconfig">Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config?</a></code>
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
            <td class="align-top">boot<wbr>Disk<wbr>Kms<wbr>Key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disk<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">guest_<wbr>accelerators</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigguestaccelerator">List[Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">image<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">local<wbr>Ssd<wbr>Count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metadata</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>cpu_<wbr>platform</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth<wbr>Scopes</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preemptible</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sandbox<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigsandboxconfig">Dict[Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>account</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">shielded_<wbr>instance_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigshieldedinstanceconfig">Dict[Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">taints</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigtaint">List[Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#nodepoolnodeconfigworkloadmetadataconfig">Dict[Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### NodePoolNodeConfigGuestAccelerator
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolNodeConfigGuestAccelerator">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolNodeConfigGuestAccelerator">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigGuestAcceleratorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigGuestAcceleratorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigGuestAcceleratorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigGuestAccelerator.html">output</a> API doc for this type.
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
            <td class="align-top">Count</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>number</code>
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
            <td class="align-top">count</td>
            <td class="align-top">
                
                <code>float</code>
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





#### NodePoolNodeConfigSandboxConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolNodeConfigSandboxConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolNodeConfigSandboxConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigSandboxConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigSandboxConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigSandboxConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigSandboxConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Sandbox<wbr>Type</td>
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
            <td class="align-top">Sandbox<wbr>Type</td>
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
            <td class="align-top">sandbox<wbr>Type</td>
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
            <td class="align-top">sandbox<wbr>Type</td>
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





#### NodePoolNodeConfigShieldedInstanceConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolNodeConfigShieldedInstanceConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolNodeConfigShieldedInstanceConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigShieldedInstanceConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigShieldedInstanceConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigShieldedInstanceConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigShieldedInstanceConfig.html">output</a> API doc for this type.
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
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>bool?</code>
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
            <td class="align-top">Enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>*bool</code>
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
            <td class="align-top">enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>boolean?</code>
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
            <td class="align-top">enable<wbr>Integrity<wbr>Monitoring</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Secure<wbr>Boot</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### NodePoolNodeConfigTaint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolNodeConfigTaint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolNodeConfigTaint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigTaintArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigTaintOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigTaintArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigTaint.html">output</a> API doc for this type.
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
            <td class="align-top">Effect</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">Value</td>
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
            <td class="align-top">Effect</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">Value</td>
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
            <td class="align-top">effect</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">value</td>
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
            <td class="align-top">effect</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
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
            <td class="align-top">value</td>
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





#### NodePoolNodeConfigWorkloadMetadataConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolNodeConfigWorkloadMetadataConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolNodeConfigWorkloadMetadataConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigWorkloadMetadataConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolNodeConfigWorkloadMetadataConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigWorkloadMetadataConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolNodeConfigWorkloadMetadataConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Node<wbr>Metadata</td>
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
            <td class="align-top">Node<wbr>Metadata</td>
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
            <td class="align-top">node<wbr>Metadata</td>
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
            <td class="align-top">node<wbr>Metadata</td>
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





#### NodePoolUpgradeSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NodePoolUpgradeSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NodePoolUpgradeSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolUpgradeSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#NodePoolUpgradeSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolUpgradeSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.NodePoolUpgradeSettings.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Surge</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unavailable</td>
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
            <td class="align-top">Max<wbr>Surge</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Unavailable</td>
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
            <td class="align-top">max<wbr>Surge</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unavailable</td>
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
            <td class="align-top">max<wbr>Surge</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Unavailable</td>
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








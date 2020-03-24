
---
title: "Cluster"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a Google Kubernetes Engine (GKE) cluster. For more information see
[the official documentation](https://cloud.google.com/container-engine/docs/clusters)
and [the API reference](https://cloud.google.com/kubernetes-engine/docs/reference/rest/v1/projects.locations.clusters).

> **Note:** All arguments and attributes, including basic auth username and
passwords as well as certificate outputs will be stored in the raw state as
plaintext. [Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

## Example Usage - with the default node pool

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const primary = new gcp.container.Cluster("primary", {
    initialNodeCount: 3,
    location: "us-central1-a",
    masterAuth: {
        clientCertificateConfig: {
            issueClientCertificate: false,
        },
        password: "",
        username: "",
    },
    nodeConfig: {
        labels: {
            foo: "bar",
        },
        metadata: {
            "disable-legacy-endpoints": "true",
        },
        oauthScopes: [
            "https://www.googleapis.com/auth/logging.write",
            "https://www.googleapis.com/auth/monitoring",
        ],
        tags: [
            "foo",
            "bar",
        ],
    },
}, {timeouts: {
    create: "30m",
    update: "40m",
}});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/container_cluster.html.markdown.



## Create a Cluster Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#Cluster">Cluster</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Cluster</span><span class="p">(resource_name, opts=None, </span>addons_config=None<span class="p">, </span>authenticator_groups_config=None<span class="p">, </span>cluster_autoscaling=None<span class="p">, </span>cluster_ipv4_cidr=None<span class="p">, </span>database_encryption=None<span class="p">, </span>default_max_pods_per_node=None<span class="p">, </span>description=None<span class="p">, </span>enable_binary_authorization=None<span class="p">, </span>enable_intranode_visibility=None<span class="p">, </span>enable_kubernetes_alpha=None<span class="p">, </span>enable_legacy_abac=None<span class="p">, </span>enable_shielded_nodes=None<span class="p">, </span>enable_tpu=None<span class="p">, </span>initial_node_count=None<span class="p">, </span>ip_allocation_policy=None<span class="p">, </span>location=None<span class="p">, </span>logging_service=None<span class="p">, </span>maintenance_policy=None<span class="p">, </span>master_auth=None<span class="p">, </span>master_authorized_networks_config=None<span class="p">, </span>min_master_version=None<span class="p">, </span>monitoring_service=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>network_policy=None<span class="p">, </span>node_config=None<span class="p">, </span>node_locations=None<span class="p">, </span>node_pools=None<span class="p">, </span>node_version=None<span class="p">, </span>pod_security_policy_config=None<span class="p">, </span>private_cluster_config=None<span class="p">, </span>project=None<span class="p">, </span>release_channel=None<span class="p">, </span>remove_default_node_pool=None<span class="p">, </span>resource_labels=None<span class="p">, </span>resource_usage_export_config=None<span class="p">, </span>subnetwork=None<span class="p">, </span>vertical_pod_autoscaling=None<span class="p">, </span>workload_identity_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.Cluster.html">Cluster</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterArgs.html">ClusterArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Cluster resource with the given unique name, arguments, and options.

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
            <td class="align-top">Addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Cluster<wbr>Ip<wbr>Allocation<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Cluster<wbr>Maintenance<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">List&lt;Cluster<wbr>Node<wbr>Pool<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">Release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Cluster<wbr>Workload<wbr>Identity<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">Addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">*Cluster<wbr>Addons<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">*Cluster<wbr>Authenticator<wbr>Groups<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">*Cluster<wbr>Cluster<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">*Cluster<wbr>Database<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">*Cluster<wbr>Ip<wbr>Allocation<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">*Cluster<wbr>Maintenance<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">*Cluster<wbr>Master<wbr>Auth</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">*Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">*Cluster<wbr>Network<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">*Cluster<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">[]Cluster<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">*Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">*Cluster<wbr>Private<wbr>Cluster<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">Release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">*Cluster<wbr>Release<wbr>Channel</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">*Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">*Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">*Cluster<wbr>Workload<wbr>Identity<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Cluster<wbr>Ip<wbr>Allocation<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Cluster<wbr>Maintenance<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">Cluster<wbr>Node<wbr>Pool[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Cluster<wbr>Workload<wbr>Identity<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">addons_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Dict[Cluster<wbr>Addons<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authenticator_<wbr>groups_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Dict[Cluster<wbr>Authenticator<wbr>Groups<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Dict[Cluster<wbr>Cluster<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>ipv4_<wbr>cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database_<wbr>encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Dict[Cluster<wbr>Database<wbr>Encryption]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>max_<wbr>pods_<wbr>per_<wbr>node</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>binary_<wbr>authorization</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>intranode_<wbr>visibility</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>kubernetes_<wbr>alpha</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>legacy_<wbr>abac</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>shielded_<wbr>nodes</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>tpu</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>allocation_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Dict[Cluster<wbr>Ip<wbr>Allocation<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">maintenance_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Dict[Cluster<wbr>Maintenance<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Dict[Cluster<wbr>Master<wbr>Auth]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>authorized_<wbr>networks_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Dict[Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>master_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitoring_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Dict[Cluster<wbr>Network<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Dict[Cluster<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">List[Cluster<wbr>Node<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod_<wbr>security_<wbr>policy_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Dict[Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>cluster_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Dict[Cluster<wbr>Private<wbr>Cluster<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">release_<wbr>channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Dict[Cluster<wbr>Release<wbr>Channel]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remove_<wbr>default_<wbr>node_<wbr>pool</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>usage_<wbr>export_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Dict[Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vertical_<wbr>pod_<wbr>autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Dict[Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload_<wbr>identity_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Dict[Cluster<wbr>Workload<wbr>Identity<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Cluster Output Properties

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
            <td class="align-top">Addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} .
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Endpoint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address of this cluster&#39;s Kubernetes master.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Cluster<wbr>Ip<wbr>Allocation<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the set of labels for this cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Cluster<wbr>Maintenance<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the cluster, unique within the project and
location.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">List&lt;Cluster<wbr>Node<wbr>Pool&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Operation</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">Release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tpu<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Cluster<wbr>Workload<wbr>Identity<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">Addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} .
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Endpoint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address of this cluster&#39;s Kubernetes master.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">*Cluster<wbr>Ip<wbr>Allocation<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the set of labels for this cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">*Cluster<wbr>Maintenance<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">*Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the cluster, unique within the project and
location.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Locations</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">[]Cluster<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Operation</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">*Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">Release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">*Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tpu<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">*Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">*Cluster<wbr>Workload<wbr>Identity<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} .
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">endpoint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address of this cluster&#39;s Kubernetes master.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial<wbr>Node<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Group<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Cluster<wbr>Ip<wbr>Allocation<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the set of labels for this cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Cluster<wbr>Maintenance<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the cluster, unique within the project and
location.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Locations</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">Cluster<wbr>Node<wbr>Pool[]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">operation</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tpu<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Cluster<wbr>Workload<wbr>Identity<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">addons_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Dict[Cluster<wbr>Addons<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authenticator_<wbr>groups_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Dict[Cluster<wbr>Authenticator<wbr>Groups<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Dict[Cluster<wbr>Cluster<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>ipv4_<wbr>cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database_<wbr>encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Dict[Cluster<wbr>Database<wbr>Encryption]</a></code>
            </td>
            <td class="align-top">{{% md %}} .
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>max_<wbr>pods_<wbr>per_<wbr>node</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>binary_<wbr>authorization</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>intranode_<wbr>visibility</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>kubernetes_<wbr>alpha</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>legacy_<wbr>abac</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>shielded_<wbr>nodes</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>tpu</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">endpoint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The IP address of this cluster&#39;s Kubernetes master.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">initial_<wbr>node_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>group_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>allocation_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Dict[Cluster<wbr>Ip<wbr>Allocation<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The fingerprint of the set of labels for this cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">maintenance_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Dict[Cluster<wbr>Maintenance<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Dict[Cluster<wbr>Master<wbr>Auth]</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>authorized_<wbr>networks_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Dict[Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>master_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitoring_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the cluster, unique within the project and
location.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Dict[Cluster<wbr>Network<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Dict[Cluster<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>locations</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">List[Cluster<wbr>Node<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">operation</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod_<wbr>security_<wbr>policy_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Dict[Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>cluster_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Dict[Cluster<wbr>Private<wbr>Cluster<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">release_<wbr>channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Dict[Cluster<wbr>Release<wbr>Channel]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remove_<wbr>default_<wbr>node_<wbr>pool</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>usage_<wbr>export_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Dict[Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services_<wbr>ipv4_<wbr>cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnetwork</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tpu_<wbr>ipv4_<wbr>cidr_<wbr>block</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vertical_<wbr>pod_<wbr>autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Dict[Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload_<wbr>identity_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Dict[Cluster<wbr>Workload<wbr>Identity<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Cluster Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/container/#Cluster">Cluster</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>addons_config=None<span class="p">, </span>authenticator_groups_config=None<span class="p">, </span>cluster_autoscaling=None<span class="p">, </span>cluster_ipv4_cidr=None<span class="p">, </span>database_encryption=None<span class="p">, </span>default_max_pods_per_node=None<span class="p">, </span>description=None<span class="p">, </span>enable_binary_authorization=None<span class="p">, </span>enable_intranode_visibility=None<span class="p">, </span>enable_kubernetes_alpha=None<span class="p">, </span>enable_legacy_abac=None<span class="p">, </span>enable_shielded_nodes=None<span class="p">, </span>enable_tpu=None<span class="p">, </span>endpoint=None<span class="p">, </span>initial_node_count=None<span class="p">, </span>instance_group_urls=None<span class="p">, </span>ip_allocation_policy=None<span class="p">, </span>label_fingerprint=None<span class="p">, </span>location=None<span class="p">, </span>logging_service=None<span class="p">, </span>maintenance_policy=None<span class="p">, </span>master_auth=None<span class="p">, </span>master_authorized_networks_config=None<span class="p">, </span>master_version=None<span class="p">, </span>min_master_version=None<span class="p">, </span>monitoring_service=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>network_policy=None<span class="p">, </span>node_config=None<span class="p">, </span>node_locations=None<span class="p">, </span>node_pools=None<span class="p">, </span>node_version=None<span class="p">, </span>operation=None<span class="p">, </span>pod_security_policy_config=None<span class="p">, </span>private_cluster_config=None<span class="p">, </span>project=None<span class="p">, </span>release_channel=None<span class="p">, </span>remove_default_node_pool=None<span class="p">, </span>resource_labels=None<span class="p">, </span>resource_usage_export_config=None<span class="p">, </span>services_ipv4_cidr=None<span class="p">, </span>subnetwork=None<span class="p">, </span>tpu_ipv4_cidr_block=None<span class="p">, </span>vertical_pod_autoscaling=None<span class="p">, </span>workload_identity_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.Cluster.html">Cluster</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterState.html">ClusterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Cluster resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Endpoint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address of this cluster&#39;s Kubernetes master.
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Cluster<wbr>Ip<wbr>Allocation<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint of the set of labels for this cluster.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Cluster<wbr>Maintenance<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">List&lt;Cluster<wbr>Node<wbr>Pool<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Operation</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">Release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tpu<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Cluster<wbr>Workload<wbr>Identity<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">Addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">*Cluster<wbr>Addons<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">*Cluster<wbr>Authenticator<wbr>Groups<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">*Cluster<wbr>Cluster<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">*Cluster<wbr>Database<wbr>Encryption</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Endpoint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address of this cluster&#39;s Kubernetes master.
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">*Cluster<wbr>Ip<wbr>Allocation<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint of the set of labels for this cluster.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logging<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">*Cluster<wbr>Maintenance<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">*Cluster<wbr>Master<wbr>Auth</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">*Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">*Cluster<wbr>Network<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">*Cluster<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">[]Cluster<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Operation</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">*Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">*Cluster<wbr>Private<wbr>Cluster<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">Release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">*Cluster<wbr>Release<wbr>Channel</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">*Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tpu<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">*Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">*Cluster<wbr>Workload<wbr>Identity<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">addons<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Cluster<wbr>Addons<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authenticator<wbr>Groups<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Cluster<wbr>Authenticator<wbr>Groups<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Cluster<wbr>Cluster<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database<wbr>Encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Cluster<wbr>Database<wbr>Encryption?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Max<wbr>Pods<wbr>Per<wbr>Node</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Binary<wbr>Authorization</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Intranode<wbr>Visibility</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Kubernetes<wbr>Alpha</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Legacy<wbr>Abac</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Shielded<wbr>Nodes</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Tpu</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">endpoint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address of this cluster&#39;s Kubernetes master.
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Allocation<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Cluster<wbr>Ip<wbr>Allocation<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Fingerprint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint of the set of labels for this cluster.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">maintenance<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Cluster<wbr>Maintenance<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Cluster<wbr>Master<wbr>Auth?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Authorized<wbr>Networks<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Master<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitoring<wbr>Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Cluster<wbr>Network<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Cluster<wbr>Node<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">Cluster<wbr>Node<wbr>Pool[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">operation</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod<wbr>Security<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Cluster<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Cluster<wbr>Private<wbr>Cluster<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">release<wbr>Channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Cluster<wbr>Release<wbr>Channel?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remove<wbr>Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Usage<wbr>Export<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services<wbr>Ipv4Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tpu<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vertical<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Identity<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Cluster<wbr>Workload<wbr>Identity<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
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
            <td class="align-top">addons_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfig">Dict[Cluster<wbr>Addons<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration for addons supported by GKE.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authenticator_<wbr>groups_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterauthenticatorgroupsconfig">Dict[Cluster<wbr>Authenticator<wbr>Groups<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[Google Groups for GKE](https://cloud.google.com/kubernetes-engine/docs/how-to/role-based-access-control#groups-setup-gsuite) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscaling">Dict[Cluster<wbr>Cluster<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Per-cluster configuration of Node Auto-Provisioning with Cluster Autoscaler to
automatically adjust the size of the cluster and create/delete node pools based
on the current needs of the cluster&#39;s workload. See the
[guide to using Node Auto-Provisioning](https://cloud.google.com/kubernetes-engine/docs/how-to/node-auto-provisioning)
for more details. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>ipv4_<wbr>cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes pods
in this cluster in CIDR notation (e.g. `10.96.0.0/14`). Leave blank to have one
automatically chosen or specify a `/14` block in `10.0.0.0/8`. This field will
only work for routes-based clusters, where `ip_allocation_policy` is not defined.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database_<wbr>encryption</td>
            <td class="align-top">
                
                <code><a href="#clusterdatabaseencryption">Dict[Cluster<wbr>Database<wbr>Encryption]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>max_<wbr>pods_<wbr>per_<wbr>node</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default maximum number of pods
per node in this cluster. This doesn&#39;t work on &#34;routes-based&#34; clusters, clusters
that don&#39;t have IP Aliasing enabled. See the [official documentation](https://cloud.google.com/kubernetes-engine/docs/how-to/flexible-pod-cidr)
for more information.
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
Description of the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>binary_<wbr>authorization</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Binary Authorization for this cluster.
If enabled, all container images will be validated by Google Binary Authorization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>intranode_<wbr>visibility</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Whether Intra-node visibility is enabled for this cluster. This makes same node pod to pod traffic visible for VPC network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>kubernetes_<wbr>alpha</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Kubernetes Alpha features for
this cluster. Note that when this option is enabled, the cluster cannot be upgraded
and will be automatically deleted after 30 days.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>legacy_<wbr>abac</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether the ABAC authorizer is enabled for this cluster.
When enabled, identities in the system, including service accounts, nodes, and controllers,
will have statically granted permissions beyond those provided by the RBAC configuration or IAM.
Defaults to `false`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>shielded_<wbr>nodes</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enable Shielded Nodes features on all nodes in this cluster.  Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>tpu</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether to enable Cloud TPU resources in this cluster.
See the [official documentation](https://cloud.google.com/tpu/docs/kubernetes-engine-setup).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">endpoint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address of this cluster&#39;s Kubernetes master.
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip_<wbr>allocation_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clusteripallocationpolicy">Dict[Cluster<wbr>Ip<wbr>Allocation<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration of cluster IP allocation for
VPC-native clusters. Adding this block enables [IP aliasing](https://cloud.google.com/kubernetes-engine/docs/how-to/ip-aliases),
making the cluster VPC-native instead of routes-based. Structure is documented
below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The fingerprint of the set of labels for this cluster.
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
The location (region or zone) in which the cluster
master will be created, as well as the default node location. If you specify a
zone (such as `us-central1-a`), the cluster will be a zonal cluster with a
single cluster master. If you specify a region (such as `us-west1`), the
cluster will be a regional cluster with multiple masters spread across zones in
the region, and with default node locations in those zones as well
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logging_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The logging service that the cluster should
write logs to. Available options include `logging.googleapis.com`(Legacy Stackdriver),
`logging.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Logging), and `none`. Defaults to `logging.googleapis.com/kubernetes`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">maintenance_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicy">Dict[Cluster<wbr>Maintenance<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maintenance policy to use for the cluster. Structure is
documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>auth</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauth">Dict[Cluster<wbr>Master<wbr>Auth]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication information for accessing the
Kubernetes master. Some values in this block are only returned by the API if
your service account has permission to get credentials for your GKE cluster. If
you see an unexpected diff removing a username/password or unsetting your client
cert, ensure you have the `container.clusters.getCredentials` permission.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>authorized_<wbr>networks_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfig">Dict[Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The desired configuration options
for master authorized networks. Omit the nested `cidr_blocks` attribute to disallow
external access (except the cluster node IPs, which GKE automatically whitelists).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current version of the master in the cluster. This may
be different than the `min_master_version` set in the config if the master
has been updated by GKE.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>master_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of the master. GKE
will auto-update the master to new versions, so this does not guarantee the
current master version--use the read-only `master_version` field to obtain that.
If unset, the cluster&#39;s version will be set by GKE to the version of the most recent
official release (which is not necessarily the latest version).  Most users will find
the `gcp.container.getEngineVersions` data source useful - it indicates which versions
are available, and can be use to approximate fuzzy versions in a
provider-compatible way. If you intend to specify versions manually,
[the docs](https://cloud.google.com/kubernetes-engine/versioning-and-upgrades#specifying_cluster_version)
describe the various acceptable formats for this field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">monitoring_<wbr>service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The monitoring service that the cluster
should write metrics to.
Automatically send metrics from pods in the cluster to the Google Cloud Monitoring API.
VM metrics will be collected by Google Compute Engine regardless of this setting
Available options include
`monitoring.googleapis.com`(Legacy Stackdriver), `monitoring.googleapis.com/kubernetes`(Stackdriver Kubernetes Engine Monitoring), and `none`.
Defaults to `monitoring.googleapis.com/kubernetes`
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
The name of the cluster, unique within the project and
location.
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
The name or self_link of the Google Compute Engine
network to which the cluster is connected. For Shared VPC, set this to the self link of the
shared network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#clusternetworkpolicy">Dict[Cluster<wbr>Network<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[NetworkPolicy](https://kubernetes.io/docs/concepts/services-networking/networkpolicies/)
feature. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfig">Dict[Cluster<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>pools</td>
            <td class="align-top">
                
                <code><a href="#clusternodepool">List[Cluster<wbr>Node<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
List of node pools associated with this cluster.
See gcp.container.NodePool for schema.
**Warning:** node pools defined inside a cluster can&#39;t be changed (or added/removed) after
cluster creation without deleting and recreating the entire cluster. Unless you absolutely need the ability
to say &#34;these are the _only_ node pools associated with this cluster&#34;, use the
gcp.container.NodePool resource instead of this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes version on the nodes. Must either be unset
or set to the same value as `min_master_version` on create. Defaults to the default
version set by GKE which is not necessarily the latest version. This only affects
nodes in the default node pool. While a fuzzy version can be specified, it&#39;s
recommended that you specify explicit versions as the provider will see spurious diffs
when fuzzy versions are used. See the `gcp.container.getEngineVersions` data source&#39;s
`version_prefix` field to approximate fuzzy versions in a provider-compatible way.
To update nodes in other node pools, use the `version` attribute on the node pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">operation</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod_<wbr>security_<wbr>policy_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterpodsecuritypolicyconfig">Dict[Cluster<wbr>Pod<wbr>Security<wbr>Policy<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[PodSecurityPolicy](https://cloud.google.com/kubernetes-engine/docs/how-to/pod-security-policies) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>cluster_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterprivateclusterconfig">Dict[Cluster<wbr>Private<wbr>Cluster<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for [private clusters](https://cloud.google.com/kubernetes-engine/docs/how-to/private-clusters),
clusters with private nodes. Structure is documented below.
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
            <td class="align-top">release_<wbr>channel</td>
            <td class="align-top">
                
                <code><a href="#clusterreleasechannel">Dict[Cluster<wbr>Release<wbr>Channel]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration options for the
[Release channel](https://cloud.google.com/kubernetes-engine/docs/concepts/release-channels)
feature, which provide more control over automatic upgrades of your GKE clusters. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">remove_<wbr>default_<wbr>node_<wbr>pool</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If `true`, deletes the default node
pool upon cluster creation. If you&#39;re using `gcp.container.NodePool`
resources with no default node pool, this should be set to `true`, alongside
setting `initial_node_count` to at least `1`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCE resource labels (a map of key/value pairs) to be applied to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>usage_<wbr>export_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfig">Dict[Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for the
[ResourceUsageExportConfig](https://cloud.google.com/kubernetes-engine/docs/how-to/cluster-usage-metering) feature.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services_<wbr>ipv4_<wbr>cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP address range of the Kubernetes services in this
cluster, in [CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`). Service addresses are typically put in the last
`/16` from the container CIDR.
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
The name or self_link of the Google Compute Engine
subnetwork in which the cluster&#39;s instances are launched.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tpu_<wbr>ipv4_<wbr>cidr_<wbr>block</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The IP address range of the Cloud TPUs in this cluster, in
[CIDR](http://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)
notation (e.g. `1.2.3.4/29`).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vertical_<wbr>pod_<wbr>autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusterverticalpodautoscaling">Dict[Cluster<wbr>Vertical<wbr>Pod<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Vertical Pod Autoscaling automatically adjusts the resources of pods controlled by it.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload_<wbr>identity_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusterworkloadidentityconfig">Dict[Cluster<wbr>Workload<wbr>Identity<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)

Workload Identity allows Kubernetes service accounts to act as a user-managed
[Google IAM Service Account](https://cloud.google.com/iam/docs/service-accounts#user-managed_service_accounts).
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ClusterAddonsConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Cloudrun<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigcloudrunconfig">Cluster<wbr>Addons<wbr>Config<wbr>Cloudrun<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Cache<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigdnscacheconfig">Cluster<wbr>Addons<wbr>Config<wbr>Dns<wbr>Cache<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Horizontal<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighorizontalpodautoscaling">Cluster<wbr>Addons<wbr>Config<wbr>Horizontal<wbr>Pod<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Load<wbr>Balancing</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighttploadbalancing">Cluster<wbr>Addons<wbr>Config<wbr>Http<wbr>Load<wbr>Balancing<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Istio<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigistioconfig">Cluster<wbr>Addons<wbr>Config<wbr>Istio<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfignetworkpolicyconfig">Cluster<wbr>Addons<wbr>Config<wbr>Network<wbr>Policy<wbr>Config<wbr>Args?</a></code>
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
            <td class="align-top">Cloudrun<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigcloudrunconfig">*Cluster<wbr>Addons<wbr>Config<wbr>Cloudrun<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Cache<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigdnscacheconfig">*Cluster<wbr>Addons<wbr>Config<wbr>Dns<wbr>Cache<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Horizontal<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighorizontalpodautoscaling">*Cluster<wbr>Addons<wbr>Config<wbr>Horizontal<wbr>Pod<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Load<wbr>Balancing</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighttploadbalancing">*Cluster<wbr>Addons<wbr>Config<wbr>Http<wbr>Load<wbr>Balancing</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Istio<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigistioconfig">*Cluster<wbr>Addons<wbr>Config<wbr>Istio<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfignetworkpolicyconfig">*Cluster<wbr>Addons<wbr>Config<wbr>Network<wbr>Policy<wbr>Config</a></code>
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
            <td class="align-top">cloudrun<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigcloudrunconfig">Cluster<wbr>Addons<wbr>Config<wbr>Cloudrun<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Cache<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigdnscacheconfig">Cluster<wbr>Addons<wbr>Config<wbr>Dns<wbr>Cache<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">horizontal<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighorizontalpodautoscaling">Cluster<wbr>Addons<wbr>Config<wbr>Horizontal<wbr>Pod<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Load<wbr>Balancing</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighttploadbalancing">Cluster<wbr>Addons<wbr>Config<wbr>Http<wbr>Load<wbr>Balancing?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">istio<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigistioconfig">Cluster<wbr>Addons<wbr>Config<wbr>Istio<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfignetworkpolicyconfig">Cluster<wbr>Addons<wbr>Config<wbr>Network<wbr>Policy<wbr>Config?</a></code>
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
            <td class="align-top">cloudrun<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigcloudrunconfig">Dict[Cluster<wbr>Addons<wbr>Config<wbr>Cloudrun<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Cache<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigdnscacheconfig">Dict[Cluster<wbr>Addons<wbr>Config<wbr>Dns<wbr>Cache<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">horizontal<wbr>Pod<wbr>Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighorizontalpodautoscaling">Dict[Cluster<wbr>Addons<wbr>Config<wbr>Horizontal<wbr>Pod<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Load<wbr>Balancing</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfighttploadbalancing">Dict[Cluster<wbr>Addons<wbr>Config<wbr>Http<wbr>Load<wbr>Balancing]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">istio<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfigistioconfig">Dict[Cluster<wbr>Addons<wbr>Config<wbr>Istio<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusteraddonsconfignetworkpolicyconfig">Dict[Cluster<wbr>Addons<wbr>Config<wbr>Network<wbr>Policy<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterAddonsConfigCloudrunConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfigCloudrunConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfigCloudrunConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigCloudrunConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigCloudrunConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigCloudrunConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigCloudrunConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">disabled</td>
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
            <td class="align-top">disabled</td>
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





#### ClusterAddonsConfigDnsCacheConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfigDnsCacheConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfigDnsCacheConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigDnsCacheConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigDnsCacheConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigDnsCacheConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigDnsCacheConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Enabled</td>
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
            <td class="align-top">Enabled</td>
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
            <td class="align-top">enabled</td>
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
            <td class="align-top">enabled</td>
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





#### ClusterAddonsConfigHorizontalPodAutoscaling
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfigHorizontalPodAutoscaling">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfigHorizontalPodAutoscaling">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigHorizontalPodAutoscalingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigHorizontalPodAutoscalingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigHorizontalPodAutoscalingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigHorizontalPodAutoscaling.html">output</a> API doc for this type.
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">disabled</td>
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
            <td class="align-top">disabled</td>
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





#### ClusterAddonsConfigHttpLoadBalancing
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfigHttpLoadBalancing">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfigHttpLoadBalancing">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigHttpLoadBalancingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigHttpLoadBalancingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigHttpLoadBalancingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigHttpLoadBalancing.html">output</a> API doc for this type.
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">disabled</td>
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
            <td class="align-top">disabled</td>
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





#### ClusterAddonsConfigIstioConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfigIstioConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfigIstioConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigIstioConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigIstioConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigIstioConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigIstioConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Auth</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
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
            <td class="align-top">Auth</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
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
            <td class="align-top">auth</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
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
            <td class="align-top">auth</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
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





#### ClusterAddonsConfigNetworkPolicyConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAddonsConfigNetworkPolicyConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAddonsConfigNetworkPolicyConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigNetworkPolicyConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAddonsConfigNetworkPolicyConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigNetworkPolicyConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAddonsConfigNetworkPolicyConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">Disabled</td>
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
            <td class="align-top">disabled</td>
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
            <td class="align-top">disabled</td>
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





#### ClusterAuthenticatorGroupsConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterAuthenticatorGroupsConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterAuthenticatorGroupsConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAuthenticatorGroupsConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterAuthenticatorGroupsConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAuthenticatorGroupsConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterAuthenticatorGroupsConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Security<wbr>Group</td>
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
            <td class="align-top">Security<wbr>Group</td>
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
            <td class="align-top">security<wbr>Group</td>
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
            <td class="align-top">security<wbr>Group</td>
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





#### ClusterClusterAutoscaling
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterClusterAutoscaling">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterClusterAutoscaling">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterClusterAutoscalingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterClusterAutoscalingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterClusterAutoscalingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterClusterAutoscaling.html">output</a> API doc for this type.
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
            <td class="align-top">Auto<wbr>Provisioning<wbr>Defaults</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingautoprovisioningdefaults">Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Auto<wbr>Provisioning<wbr>Defaults<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscaling<wbr>Profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Limits</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingresourcelimit">List&lt;Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Resource<wbr>Limit<wbr>Args&gt;?</a></code>
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
            <td class="align-top">Auto<wbr>Provisioning<wbr>Defaults</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingautoprovisioningdefaults">*Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Auto<wbr>Provisioning<wbr>Defaults</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscaling<wbr>Profile</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Limits</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingresourcelimit">[]Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Resource<wbr>Limit</a></code>
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
            <td class="align-top">auto<wbr>Provisioning<wbr>Defaults</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingautoprovisioningdefaults">Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Auto<wbr>Provisioning<wbr>Defaults?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscaling<wbr>Profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Limits</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingresourcelimit">Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Resource<wbr>Limit[]?</a></code>
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
            <td class="align-top">auto<wbr>Provisioning<wbr>Defaults</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingautoprovisioningdefaults">Dict[Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Auto<wbr>Provisioning<wbr>Defaults]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscaling<wbr>Profile</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Limits</td>
            <td class="align-top">
                
                <code><a href="#clusterclusterautoscalingresourcelimit">List[Cluster<wbr>Cluster<wbr>Autoscaling<wbr>Resource<wbr>Limit]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterClusterAutoscalingAutoProvisioningDefaults
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterClusterAutoscalingAutoProvisioningDefaults">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterClusterAutoscalingAutoProvisioningDefaults">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterClusterAutoscalingAutoProvisioningDefaultsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterClusterAutoscalingAutoProvisioningDefaultsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterClusterAutoscalingAutoProvisioningDefaultsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterClusterAutoscalingAutoProvisioningDefaults.html">output</a> API doc for this type.
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
            <td class="align-top">Service<wbr>Account</td>
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
            <td class="align-top">Service<wbr>Account</td>
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
            <td class="align-top">service<wbr>Account</td>
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
            <td class="align-top">service_<wbr>account</td>
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





#### ClusterClusterAutoscalingResourceLimit
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterClusterAutoscalingResourceLimit">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterClusterAutoscalingResourceLimit">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterClusterAutoscalingResourceLimitArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterClusterAutoscalingResourceLimitOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterClusterAutoscalingResourceLimitArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterClusterAutoscalingResourceLimit.html">output</a> API doc for this type.
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
            <td class="align-top">Maximum</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimum</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Type</td>
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
            <td class="align-top">Maximum</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimum</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Type</td>
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
            <td class="align-top">maximum</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimum</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Type</td>
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
            <td class="align-top">maximum</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimum</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Type</td>
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





#### ClusterDatabaseEncryption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterDatabaseEncryption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterDatabaseEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterDatabaseEncryptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterDatabaseEncryptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterDatabaseEncryptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterDatabaseEncryption.html">output</a> API doc for this type.
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
            <td class="align-top">Key<wbr>Name</td>
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
            <td class="align-top">Key<wbr>Name</td>
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
            <td class="align-top">key<wbr>Name</td>
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
            <td class="align-top">key<wbr>Name</td>
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
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterIpAllocationPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterIpAllocationPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterIpAllocationPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterIpAllocationPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterIpAllocationPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterIpAllocationPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterIpAllocationPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Cluster<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Secondary<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Secondary<wbr>Range<wbr>Name</td>
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
            <td class="align-top">Cluster<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Secondary<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Services<wbr>Secondary<wbr>Range<wbr>Name</td>
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
            <td class="align-top">cluster<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Secondary<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services<wbr>Secondary<wbr>Range<wbr>Name</td>
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
            <td class="align-top">cluster<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Secondary<wbr>Range<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">services<wbr>Secondary<wbr>Range<wbr>Name</td>
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





#### ClusterMaintenancePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMaintenancePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMaintenancePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMaintenancePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMaintenancePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMaintenancePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMaintenancePolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Daily<wbr>Maintenance<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicydailymaintenancewindow">Cluster<wbr>Maintenance<wbr>Policy<wbr>Daily<wbr>Maintenance<wbr>Window<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurring<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicyrecurringwindow">Cluster<wbr>Maintenance<wbr>Policy<wbr>Recurring<wbr>Window<wbr>Args?</a></code>
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
            <td class="align-top">Daily<wbr>Maintenance<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicydailymaintenancewindow">*Cluster<wbr>Maintenance<wbr>Policy<wbr>Daily<wbr>Maintenance<wbr>Window</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurring<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicyrecurringwindow">*Cluster<wbr>Maintenance<wbr>Policy<wbr>Recurring<wbr>Window</a></code>
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
            <td class="align-top">daily<wbr>Maintenance<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicydailymaintenancewindow">Cluster<wbr>Maintenance<wbr>Policy<wbr>Daily<wbr>Maintenance<wbr>Window?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurring<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicyrecurringwindow">Cluster<wbr>Maintenance<wbr>Policy<wbr>Recurring<wbr>Window?</a></code>
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
            <td class="align-top">daily<wbr>Maintenance<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicydailymaintenancewindow">Dict[Cluster<wbr>Maintenance<wbr>Policy<wbr>Daily<wbr>Maintenance<wbr>Window]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurring<wbr>Window</td>
            <td class="align-top">
                
                <code><a href="#clustermaintenancepolicyrecurringwindow">Dict[Cluster<wbr>Maintenance<wbr>Policy<wbr>Recurring<wbr>Window]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterMaintenancePolicyDailyMaintenanceWindow
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMaintenancePolicyDailyMaintenanceWindow">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMaintenancePolicyDailyMaintenanceWindow">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMaintenancePolicyDailyMaintenanceWindowArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMaintenancePolicyDailyMaintenanceWindowOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMaintenancePolicyDailyMaintenanceWindowArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMaintenancePolicyDailyMaintenanceWindow.html">output</a> API doc for this type.
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
            <td class="align-top">Duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Start<wbr>Time</td>
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
            <td class="align-top">Duration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Start<wbr>Time</td>
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
            <td class="align-top">duration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">start<wbr>Time</td>
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
            <td class="align-top">duration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">start<wbr>Time</td>
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





#### ClusterMaintenancePolicyRecurringWindow
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMaintenancePolicyRecurringWindow">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMaintenancePolicyRecurringWindow">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMaintenancePolicyRecurringWindowArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMaintenancePolicyRecurringWindowOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMaintenancePolicyRecurringWindowArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMaintenancePolicyRecurringWindow.html">output</a> API doc for this type.
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
            <td class="align-top">End<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Start<wbr>Time</td>
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
            <td class="align-top">End<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Start<wbr>Time</td>
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
            <td class="align-top">end<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">start<wbr>Time</td>
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
            <td class="align-top">end<wbr>Time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">start<wbr>Time</td>
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





#### ClusterMasterAuth
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMasterAuth">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMasterAuth">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuth.html">output</a> API doc for this type.
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
            <td class="align-top">Client<wbr>Certificate</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Client<wbr>Certificate<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthclientcertificateconfig">Cluster<wbr>Master<wbr>Auth<wbr>Client<wbr>Certificate<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Client<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ca<wbr>Certificate</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">Client<wbr>Certificate</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Client<wbr>Certificate<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthclientcertificateconfig">*Cluster<wbr>Master<wbr>Auth<wbr>Client<wbr>Certificate<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Client<wbr>Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Ca<wbr>Certificate</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">client<wbr>Certificate</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">client<wbr>Certificate<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthclientcertificateconfig">Cluster<wbr>Master<wbr>Auth<wbr>Client<wbr>Certificate<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">client<wbr>Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Ca<wbr>Certificate</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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
            <td class="align-top">client<wbr>Certificate</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">client<wbr>Certificate<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthclientcertificateconfig">Dict[Cluster<wbr>Master<wbr>Auth<wbr>Client<wbr>Certificate<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">client<wbr>Key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Ca<wbr>Certificate</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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





#### ClusterMasterAuthClientCertificateConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMasterAuthClientCertificateConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMasterAuthClientCertificateConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthClientCertificateConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthClientCertificateConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthClientCertificateConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthClientCertificateConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Issue<wbr>Client<wbr>Certificate</td>
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
            <td class="align-top">Issue<wbr>Client<wbr>Certificate</td>
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
            <td class="align-top">issue<wbr>Client<wbr>Certificate</td>
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
            <td class="align-top">issue<wbr>Client<wbr>Certificate</td>
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





#### ClusterMasterAuthorizedNetworksConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMasterAuthorizedNetworksConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMasterAuthorizedNetworksConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthorizedNetworksConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthorizedNetworksConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthorizedNetworksConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthorizedNetworksConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Cidr<wbr>Blocks</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfigcidrblock">List&lt;Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config<wbr>Cidr<wbr>Block<wbr>Args&gt;?</a></code>
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
            <td class="align-top">Cidr<wbr>Blocks</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfigcidrblock">[]Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config<wbr>Cidr<wbr>Block</a></code>
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
            <td class="align-top">cidr<wbr>Blocks</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfigcidrblock">Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config<wbr>Cidr<wbr>Block[]?</a></code>
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
            <td class="align-top">cidr<wbr>Blocks</td>
            <td class="align-top">
                
                <code><a href="#clustermasterauthorizednetworksconfigcidrblock">List[Cluster<wbr>Master<wbr>Authorized<wbr>Networks<wbr>Config<wbr>Cidr<wbr>Block]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterMasterAuthorizedNetworksConfigCidrBlock
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterMasterAuthorizedNetworksConfigCidrBlock">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterMasterAuthorizedNetworksConfigCidrBlock">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthorizedNetworksConfigCidrBlockArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterMasterAuthorizedNetworksConfigCidrBlockOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthorizedNetworksConfigCidrBlockArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterMasterAuthorizedNetworksConfigCidrBlock.html">output</a> API doc for this type.
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
            <td class="align-top">Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
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
            <td class="align-top">Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
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
            <td class="align-top">cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
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
            <td class="align-top">cidr_<wbr>block</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
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





#### ClusterNetworkPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNetworkPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNetworkPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNetworkPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNetworkPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNetworkPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNetworkPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provider</td>
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
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Provider</td>
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
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provider</td>
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
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">provider</td>
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





#### ClusterNodeConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodeConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodeConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfig.html">output</a> API doc for this type.
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
                
                <code><a href="#clusternodeconfigguestaccelerator">List&lt;Cluster<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator<wbr>Args&gt;?</a></code>
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
                
                <code><a href="#clusternodeconfigsandboxconfig">Cluster<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodeconfigshieldedinstanceconfig">Cluster<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodeconfigtaint">List&lt;Cluster<wbr>Node<wbr>Config<wbr>Taint<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfigworkloadmetadataconfig">Cluster<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodeconfigguestaccelerator">[]Cluster<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator</a></code>
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
                
                <code><a href="#clusternodeconfigsandboxconfig">*Cluster<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config</a></code>
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
                
                <code><a href="#clusternodeconfigshieldedinstanceconfig">*Cluster<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config</a></code>
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
                
                <code><a href="#clusternodeconfigtaint">[]Cluster<wbr>Node<wbr>Config<wbr>Taint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfigworkloadmetadataconfig">*Cluster<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config</a></code>
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
                
                <code><a href="#clusternodeconfigguestaccelerator">Cluster<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator[]?</a></code>
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
                
                <code><a href="#clusternodeconfigsandboxconfig">Cluster<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config?</a></code>
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
                
                <code><a href="#clusternodeconfigshieldedinstanceconfig">Cluster<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config?</a></code>
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
                
                <code><a href="#clusternodeconfigtaint">Cluster<wbr>Node<wbr>Config<wbr>Taint[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfigworkloadmetadataconfig">Cluster<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config?</a></code>
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
                
                <code><a href="#clusternodeconfigguestaccelerator">List[Cluster<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator]</a></code>
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
                
                <code><a href="#clusternodeconfigsandboxconfig">Dict[Cluster<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config]</a></code>
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
                
                <code><a href="#clusternodeconfigshieldedinstanceconfig">Dict[Cluster<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config]</a></code>
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
                
                <code><a href="#clusternodeconfigtaint">List[Cluster<wbr>Node<wbr>Config<wbr>Taint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodeconfigworkloadmetadataconfig">Dict[Cluster<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterNodeConfigGuestAccelerator
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodeConfigGuestAccelerator">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodeConfigGuestAccelerator">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigGuestAcceleratorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigGuestAcceleratorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigGuestAcceleratorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigGuestAccelerator.html">output</a> API doc for this type.
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





#### ClusterNodeConfigSandboxConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodeConfigSandboxConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodeConfigSandboxConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigSandboxConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigSandboxConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigSandboxConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigSandboxConfig.html">output</a> API doc for this type.
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





#### ClusterNodeConfigShieldedInstanceConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodeConfigShieldedInstanceConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodeConfigShieldedInstanceConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigShieldedInstanceConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigShieldedInstanceConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigShieldedInstanceConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigShieldedInstanceConfig.html">output</a> API doc for this type.
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





#### ClusterNodeConfigTaint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodeConfigTaint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodeConfigTaint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigTaintArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigTaintOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigTaintArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigTaint.html">output</a> API doc for this type.
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





#### ClusterNodeConfigWorkloadMetadataConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodeConfigWorkloadMetadataConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodeConfigWorkloadMetadataConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigWorkloadMetadataConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodeConfigWorkloadMetadataConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigWorkloadMetadataConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodeConfigWorkloadMetadataConfig.html">output</a> API doc for this type.
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





#### ClusterNodePool
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePool">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePool">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePool.html">output</a> API doc for this type.
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
            <td class="align-top">Autoscaling</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolautoscaling">Cluster<wbr>Node<wbr>Pool<wbr>Autoscaling<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolmanagement">Cluster<wbr>Node<wbr>Pool<wbr>Management<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the cluster, unique within the project and
location.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolupgradesettings">Cluster<wbr>Node<wbr>Pool<wbr>Upgrade<wbr>Settings<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodepoolautoscaling">*Cluster<wbr>Node<wbr>Pool<wbr>Autoscaling</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Management</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolmanagement">*Cluster<wbr>Node<wbr>Pool<wbr>Management</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the cluster, unique within the project and
location.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfig">*Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolupgradesettings">*Cluster<wbr>Node<wbr>Pool<wbr>Upgrade<wbr>Settings</a></code>
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
                
                <code><a href="#clusternodepoolautoscaling">Cluster<wbr>Node<wbr>Pool<wbr>Autoscaling?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolmanagement">Cluster<wbr>Node<wbr>Pool<wbr>Management?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the cluster, unique within the project and
location.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolupgradesettings">Cluster<wbr>Node<wbr>Pool<wbr>Upgrade<wbr>Settings?</a></code>
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
                
                <code><a href="#clusternodepoolautoscaling">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Autoscaling]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The number of nodes to create in this
cluster&#39;s default node pool. In regional or multi-zonal clusters, this is the
number of nodes per zone. Must be set if `node_pool` is not set. If you&#39;re using
`gcp.container.NodePool` objects with no default node pool, you&#39;ll need to
set this to a value of at least `1`, alongside setting
`remove_default_node_pool` to `true`.
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
List of instance group URLs which have been assigned
to the cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">management</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolmanagement">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Management]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The name of the cluster, unique within the project and
location.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfig">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters used in creating the default node pool.
Generally, this field should not be used at the same time as a
`gcp.container.NodePool` or a `node_pool` block; this configuration
manages the default node pool, which isn&#39;t recommended to be used with
this provider. Structure is documented below.
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
The list of zones in which the cluster&#39;s nodes
are located. Nodes must be in the region of their regional cluster or in the
same region as their cluster&#39;s zone for zonal clusters. If this is specified for
a zonal cluster, omit the cluster&#39;s zone.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upgrade_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolupgradesettings">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Upgrade<wbr>Settings]</a></code>
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterNodePoolAutoscaling
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolAutoscaling">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolAutoscaling">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolAutoscalingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolAutoscalingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolAutoscalingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolAutoscaling.html">output</a> API doc for this type.
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





#### ClusterNodePoolManagement
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolManagement">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolManagement">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolManagementArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolManagementOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolManagementArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolManagement.html">output</a> API doc for this type.
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





#### ClusterNodePoolNodeConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolNodeConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolNodeConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfig.html">output</a> API doc for this type.
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
                
                <code><a href="#clusternodepoolnodeconfigguestaccelerator">List&lt;Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator<wbr>Args&gt;?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigsandboxconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigshieldedinstanceconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigtaint">List&lt;Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfigworkloadmetadataconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config<wbr>Args?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigguestaccelerator">[]Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigsandboxconfig">*Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigshieldedinstanceconfig">*Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigtaint">[]Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfigworkloadmetadataconfig">*Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigguestaccelerator">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator[]?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigsandboxconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigshieldedinstanceconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigtaint">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfigworkloadmetadataconfig">Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config?</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigguestaccelerator">List[Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Guest<wbr>Accelerator]</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigsandboxconfig">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Sandbox<wbr>Config]</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigshieldedinstanceconfig">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Shielded<wbr>Instance<wbr>Config]</a></code>
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
                
                <code><a href="#clusternodepoolnodeconfigtaint">List[Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Taint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workload<wbr>Metadata<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#clusternodepoolnodeconfigworkloadmetadataconfig">Dict[Cluster<wbr>Node<wbr>Pool<wbr>Node<wbr>Config<wbr>Workload<wbr>Metadata<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ClusterNodePoolNodeConfigGuestAccelerator
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolNodeConfigGuestAccelerator">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolNodeConfigGuestAccelerator">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigGuestAcceleratorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigGuestAcceleratorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigGuestAcceleratorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigGuestAccelerator.html">output</a> API doc for this type.
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





#### ClusterNodePoolNodeConfigSandboxConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolNodeConfigSandboxConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolNodeConfigSandboxConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigSandboxConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigSandboxConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigSandboxConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigSandboxConfig.html">output</a> API doc for this type.
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





#### ClusterNodePoolNodeConfigShieldedInstanceConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolNodeConfigShieldedInstanceConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolNodeConfigShieldedInstanceConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigShieldedInstanceConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigShieldedInstanceConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigShieldedInstanceConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigShieldedInstanceConfig.html">output</a> API doc for this type.
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





#### ClusterNodePoolNodeConfigTaint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolNodeConfigTaint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolNodeConfigTaint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigTaintArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigTaintOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigTaintArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigTaint.html">output</a> API doc for this type.
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





#### ClusterNodePoolNodeConfigWorkloadMetadataConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolNodeConfigWorkloadMetadataConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolNodeConfigWorkloadMetadataConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigWorkloadMetadataConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolNodeConfigWorkloadMetadataConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigWorkloadMetadataConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolNodeConfigWorkloadMetadataConfig.html">output</a> API doc for this type.
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





#### ClusterNodePoolUpgradeSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterNodePoolUpgradeSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterNodePoolUpgradeSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolUpgradeSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterNodePoolUpgradeSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolUpgradeSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterNodePoolUpgradeSettings.html">output</a> API doc for this type.
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





#### ClusterPodSecurityPolicyConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterPodSecurityPolicyConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterPodSecurityPolicyConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterPodSecurityPolicyConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterPodSecurityPolicyConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterPodSecurityPolicyConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterPodSecurityPolicyConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Enabled</td>
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
            <td class="align-top">Enabled</td>
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
            <td class="align-top">enabled</td>
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
            <td class="align-top">enabled</td>
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





#### ClusterPrivateClusterConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterPrivateClusterConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterPrivateClusterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterPrivateClusterConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterPrivateClusterConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterPrivateClusterConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterPrivateClusterConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Enable<wbr>Private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Private<wbr>Nodes</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Endpoint</td>
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
            <td class="align-top">Enable<wbr>Private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Private<wbr>Nodes</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Master<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Peering<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Endpoint</td>
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
            <td class="align-top">enable<wbr>Private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Private<wbr>Nodes</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Endpoint</td>
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
            <td class="align-top">enable<wbr>Private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Private<wbr>Nodes</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">master<wbr>Ipv4Cidr<wbr>Block</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">peering<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Endpoint</td>
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





#### ClusterReleaseChannel
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterReleaseChannel">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterReleaseChannel">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterReleaseChannelArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterReleaseChannelOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterReleaseChannelArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterReleaseChannel.html">output</a> API doc for this type.
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
            <td class="align-top">Channel</td>
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
            <td class="align-top">Channel</td>
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
            <td class="align-top">channel</td>
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
            <td class="align-top">channel</td>
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





#### ClusterResourceUsageExportConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterResourceUsageExportConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterResourceUsageExportConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterResourceUsageExportConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterResourceUsageExportConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterResourceUsageExportConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterResourceUsageExportConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Bigquery<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfigbigquerydestination">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config<wbr>Bigquery<wbr>Destination<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Network<wbr>Egress<wbr>Metering</td>
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
            <td class="align-top">Bigquery<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfigbigquerydestination">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config<wbr>Bigquery<wbr>Destination</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Network<wbr>Egress<wbr>Metering</td>
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
            <td class="align-top">bigquery<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfigbigquerydestination">Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config<wbr>Bigquery<wbr>Destination</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Network<wbr>Egress<wbr>Metering</td>
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
            <td class="align-top">bigquery<wbr>Destination</td>
            <td class="align-top">
                
                <code><a href="#clusterresourceusageexportconfigbigquerydestination">Dict[Cluster<wbr>Resource<wbr>Usage<wbr>Export<wbr>Config<wbr>Bigquery<wbr>Destination]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Network<wbr>Egress<wbr>Metering</td>
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





#### ClusterResourceUsageExportConfigBigqueryDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterResourceUsageExportConfigBigqueryDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterResourceUsageExportConfigBigqueryDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterResourceUsageExportConfigBigqueryDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterResourceUsageExportConfigBigqueryDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterResourceUsageExportConfigBigqueryDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterResourceUsageExportConfigBigqueryDestination.html">output</a> API doc for this type.
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
            <td class="align-top">Dataset<wbr>Id</td>
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
            <td class="align-top">Dataset<wbr>Id</td>
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
            <td class="align-top">dataset<wbr>Id</td>
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
            <td class="align-top">dataset_<wbr>id</td>
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





#### ClusterVerticalPodAutoscaling
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterVerticalPodAutoscaling">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterVerticalPodAutoscaling">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterVerticalPodAutoscalingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterVerticalPodAutoscalingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterVerticalPodAutoscalingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterVerticalPodAutoscaling.html">output</a> API doc for this type.
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
            <td class="align-top">Enabled</td>
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
            <td class="align-top">Enabled</td>
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
            <td class="align-top">enabled</td>
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
            <td class="align-top">enabled</td>
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





#### ClusterWorkloadIdentityConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ClusterWorkloadIdentityConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ClusterWorkloadIdentityConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterWorkloadIdentityConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/container?tab=doc#ClusterWorkloadIdentityConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterWorkloadIdentityConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Container.ClusterWorkloadIdentityConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Identity<wbr>Namespace</td>
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
            <td class="align-top">Identity<wbr>Namespace</td>
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
            <td class="align-top">identity<wbr>Namespace</td>
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
            <td class="align-top">identity<wbr>Namespace</td>
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








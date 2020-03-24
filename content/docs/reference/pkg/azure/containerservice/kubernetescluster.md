
---
title: "KubernetesCluster"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a Managed Kubernetes Cluster (also known as AKS / Azure Kubernetes Service)

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/kubernetes_cluster.html.markdown.



## Create a KubernetesCluster Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/containerservice/#KubernetesCluster">KubernetesCluster</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/containerservice/#KubernetesClusterArgs">KubernetesClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">KubernetesCluster</span><span class="p">(resource_name, opts=None, </span>addon_profile=None<span class="p">, </span>api_server_authorized_ip_ranges=None<span class="p">, </span>default_node_pool=None<span class="p">, </span>dns_prefix=None<span class="p">, </span>enable_pod_security_policy=None<span class="p">, </span>identity=None<span class="p">, </span>kubernetes_version=None<span class="p">, </span>linux_profile=None<span class="p">, </span>location=None<span class="p">, </span>name=None<span class="p">, </span>network_profile=None<span class="p">, </span>node_resource_group=None<span class="p">, </span>private_link_enabled=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>role_based_access_control=None<span class="p">, </span>service_principal=None<span class="p">, </span>tags=None<span class="p">, </span>windows_profile=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewKubernetesCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterArgs">KubernetesClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesCluster">KubernetesCluster</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesCluster.html">KubernetesCluster</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterArgs.html">KubernetesClusterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a KubernetesCluster resource with the given unique name, arguments, and options.

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
            <td class="align-top">Addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Kubernetes<wbr>Cluster<wbr>Identity<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
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
            <td class="align-top">Addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">*Kubernetes<wbr>Cluster<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">*Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">*Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">*Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">*Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
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
            <td class="align-top">addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Kubernetes<wbr>Cluster<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
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
            <td class="align-top">addon_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">api_<wbr>server_<wbr>authorized_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>node_<wbr>pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Dict[Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>pod_<wbr>security_<wbr>policy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Dict[Kubernetes<wbr>Cluster<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kubernetes_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linux_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Dict[Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Dict[Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>resource_<wbr>group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>link_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role_<wbr>based_<wbr>access_<wbr>control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Dict[Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Dict[Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">windows_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Dict[Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## KubernetesCluster Output Properties

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
            <td class="align-top">Addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fqdn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Kubernetes<wbr>Cluster<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">List&lt;Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">List&lt;Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `linux_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Fqdn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control</a></code>
            </td>
            <td class="align-top">{{% md %}} A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal</a></code>
            </td>
            <td class="align-top">{{% md %}} A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `windows_profile` block as defined below.
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
            <td class="align-top">Addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fqdn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">*Kubernetes<wbr>Cluster<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">[]Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">[]Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">*Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `linux_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Fqdn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control</a></code>
            </td>
            <td class="align-top">{{% md %}} A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal</a></code>
            </td>
            <td class="align-top">{{% md %}} A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">*Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `windows_profile` block as defined below.
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
            <td class="align-top">addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fqdn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Kubernetes<wbr>Cluster<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Admin<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Admin<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `linux_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Fqdn</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control</a></code>
            </td>
            <td class="align-top">{{% md %}} A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal</a></code>
            </td>
            <td class="align-top">{{% md %}} A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `windows_profile` block as defined below.
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
            <td class="align-top">addon_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">api_<wbr>server_<wbr>authorized_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>node_<wbr>pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Dict[Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>pod_<wbr>security_<wbr>policy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fqdn</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Dict[Kubernetes<wbr>Cluster<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>admin_<wbr>config_<wbr>raw</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>admin_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">List[Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>config_<wbr>raw</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">List[Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kubernetes_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linux_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Dict[Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `linux_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Dict[Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>resource_<wbr>group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>fqdn</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>link_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role_<wbr>based_<wbr>access_<wbr>control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Dict[Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Dict[Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">windows_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Dict[Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `windows_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing KubernetesCluster Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/containerservice/#KubernetesClusterState">KubernetesClusterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/containerservice/#KubernetesCluster">KubernetesCluster</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>addon_profile=None<span class="p">, </span>api_server_authorized_ip_ranges=None<span class="p">, </span>default_node_pool=None<span class="p">, </span>dns_prefix=None<span class="p">, </span>enable_pod_security_policy=None<span class="p">, </span>fqdn=None<span class="p">, </span>identity=None<span class="p">, </span>kube_admin_config_raw=None<span class="p">, </span>kube_admin_configs=None<span class="p">, </span>kube_config_raw=None<span class="p">, </span>kube_configs=None<span class="p">, </span>kubernetes_version=None<span class="p">, </span>linux_profile=None<span class="p">, </span>location=None<span class="p">, </span>name=None<span class="p">, </span>network_profile=None<span class="p">, </span>node_resource_group=None<span class="p">, </span>private_fqdn=None<span class="p">, </span>private_link_enabled=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>role_based_access_control=None<span class="p">, </span>service_principal=None<span class="p">, </span>tags=None<span class="p">, </span>windows_profile=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetKubernetesCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterState">KubernetesClusterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesCluster">KubernetesCluster</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesCluster.html">KubernetesCluster</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterState.html">KubernetesClusterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing KubernetesCluster resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fqdn</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Kubernetes<wbr>Cluster<wbr>Identity<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">List&lt;Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">List&lt;Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Fqdn</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
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
            <td class="align-top">Addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">*Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fqdn</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">*Kubernetes<wbr>Cluster<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Admin<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">[]Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">[]Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">*Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">*Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Fqdn</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">*Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">*Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">*Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
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
            <td class="align-top">addon<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">api<wbr>Server<wbr>Authorized<wbr>Ip<wbr>Ranges</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Node<wbr>Pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns<wbr>Prefix</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Pod<wbr>Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fqdn</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Kubernetes<wbr>Cluster<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Admin<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Admin<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Config<wbr>Raw</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kubernetes<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linux<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Resource<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Fqdn</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Link<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Based<wbr>Access<wbr>Control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">windows<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
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
            <td class="align-top">addon_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofile">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `addon_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">api_<wbr>server_<wbr>authorized_<wbr>ip_<wbr>ranges</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The IP ranges to whitelist for incoming traffic to the masters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>node_<wbr>pool</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterdefaultnodepool">Dict[Kubernetes<wbr>Cluster<wbr>Default<wbr>Node<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `default_node_pool` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dns_<wbr>prefix</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
DNS prefix specified when creating the managed cluster. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>pod_<wbr>security_<wbr>policy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether Pod Security Policies are enabled. Note that this also requires role based access control to be enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fqdn</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN of the Azure Kubernetes Managed Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteridentity">Dict[Kubernetes<wbr>Cluster<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>admin_<wbr>config_<wbr>raw</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config for the admin account to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>admin_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeadminconfig">List[Kubernetes<wbr>Cluster<wbr>Kube<wbr>Admin<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_admin_config` block as defined below. This is only available when Role Based Access Control with Azure Active Directory is enabled.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>config_<wbr>raw</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Raw Kubernetes config to be used by [kubectl](https://kubernetes.io/docs/reference/kubectl/overview/) and other compatible tools
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterkubeconfig">List[Kubernetes<wbr>Cluster<wbr>Kube<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `kube_config` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kubernetes_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Version of Kubernetes specified when creating the AKS managed cluster. If not specified, the latest recommended version will be used at provisioning time (but won&#39;t auto-upgrade).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linux_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofile">Dict[Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `linux_profile` block as defined below.
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
The location where the Managed Kubernetes Cluster should be created. Changing this forces a new resource to be created.
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
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofile">Dict[Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `network_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>resource_<wbr>group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Resource Group where the Kubernetes Nodes should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>fqdn</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The FQDN for the Kubernetes Cluster when private link has been enabled, which is only resolvable inside the Virtual Network used by the Kubernetes Cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>link_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Resource Group where the Managed Kubernetes Cluster should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role_<wbr>based_<wbr>access_<wbr>control</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrol">Dict[Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `role_based_access_control` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>principal</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterserviceprincipal">Dict[Kubernetes<wbr>Cluster<wbr>Service<wbr>Principal]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `service_principal` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">windows_<wbr>profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterwindowsprofile">Dict[Kubernetes<wbr>Cluster<wbr>Windows<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `windows_profile` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### KubernetesClusterAddonProfile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterAddonProfile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterAddonProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfile.html">output</a> API doc for this type.
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
            <td class="align-top">Aci<wbr>Connector<wbr>Linux</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileaciconnectorlinux">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Aci<wbr>Connector<wbr>Linux<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileazurepolicy">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Azure<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Application<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilehttpapplicationrouting">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Http<wbr>Application<wbr>Routing<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `http_application_routing` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Dashboard</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilekubedashboard">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Kube<wbr>Dashboard<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oms<wbr>Agent</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileomsagent">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Oms<wbr>Agent<wbr>Args?</a></code>
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
            <td class="align-top">Aci<wbr>Connector<wbr>Linux</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileaciconnectorlinux">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Aci<wbr>Connector<wbr>Linux</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileazurepolicy">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Azure<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Application<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilehttpapplicationrouting">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Http<wbr>Application<wbr>Routing</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `http_application_routing` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Kube<wbr>Dashboard</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilekubedashboard">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Kube<wbr>Dashboard</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oms<wbr>Agent</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileomsagent">*Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Oms<wbr>Agent</a></code>
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
            <td class="align-top">aci<wbr>Connector<wbr>Linux</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileaciconnectorlinux">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Aci<wbr>Connector<wbr>Linux?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileazurepolicy">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Azure<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Application<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilehttpapplicationrouting">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Http<wbr>Application<wbr>Routing?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `http_application_routing` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Dashboard</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilekubedashboard">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Kube<wbr>Dashboard?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oms<wbr>Agent</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileomsagent">Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Oms<wbr>Agent?</a></code>
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
            <td class="align-top">aci<wbr>Connector<wbr>Linux</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileaciconnectorlinux">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Aci<wbr>Connector<wbr>Linux]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileazurepolicy">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Azure<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Application<wbr>Routing</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilehttpapplicationrouting">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Http<wbr>Application<wbr>Routing]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `http_application_routing` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">kube<wbr>Dashboard</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofilekubedashboard">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Kube<wbr>Dashboard]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oms<wbr>Agent</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusteraddonprofileomsagent">Dict[Kubernetes<wbr>Cluster<wbr>Addon<wbr>Profile<wbr>Oms<wbr>Agent]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterAddonProfileAciConnectorLinux
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterAddonProfileAciConnectorLinux">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterAddonProfileAciConnectorLinux">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileAciConnectorLinuxArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileAciConnectorLinuxOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileAciConnectorLinuxArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileAciConnectorLinux.html">output</a> API doc for this type.
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
            <td class="align-top">Subnet<wbr>Name</td>
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
            <td class="align-top">Subnet<wbr>Name</td>
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
            <td class="align-top">subnet<wbr>Name</td>
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
            <td class="align-top">subnet<wbr>Name</td>
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





#### KubernetesClusterAddonProfileAzurePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterAddonProfileAzurePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterAddonProfileAzurePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileAzurePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileAzurePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileAzurePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileAzurePolicy.html">output</a> API doc for this type.
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





#### KubernetesClusterAddonProfileHttpApplicationRouting
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterAddonProfileHttpApplicationRouting">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterAddonProfileHttpApplicationRouting">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileHttpApplicationRoutingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileHttpApplicationRoutingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileHttpApplicationRoutingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileHttpApplicationRouting.html">output</a> API doc for this type.
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
            <td class="align-top">Http<wbr>Application<wbr>Routing<wbr>Zone<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Zone Name of the HTTP Application Routing.
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
            <td class="align-top">Http<wbr>Application<wbr>Routing<wbr>Zone<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Zone Name of the HTTP Application Routing.
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
            <td class="align-top">http<wbr>Application<wbr>Routing<wbr>Zone<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Zone Name of the HTTP Application Routing.
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
            <td class="align-top">http<wbr>Application<wbr>Routing<wbr>Zone<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Zone Name of the HTTP Application Routing.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterAddonProfileKubeDashboard
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterAddonProfileKubeDashboard">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterAddonProfileKubeDashboard">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileKubeDashboardArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileKubeDashboardOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileKubeDashboardArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileKubeDashboard.html">output</a> API doc for this type.
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





#### KubernetesClusterAddonProfileOmsAgent
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterAddonProfileOmsAgent">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterAddonProfileOmsAgent">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileOmsAgentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterAddonProfileOmsAgentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileOmsAgentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterAddonProfileOmsAgent.html">output</a> API doc for this type.
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
            <td class="align-top">Log<wbr>Analytics<wbr>Workspace<wbr>Id</td>
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
            <td class="align-top">Log<wbr>Analytics<wbr>Workspace<wbr>Id</td>
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
            <td class="align-top">log<wbr>Analytics<wbr>Workspace<wbr>Id</td>
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
            <td class="align-top">log_<wbr>analytics_<wbr>workspace_<wbr>id</td>
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





#### KubernetesClusterDefaultNodePool
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterDefaultNodePool">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterDefaultNodePool">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterDefaultNodePoolArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterDefaultNodePoolOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterDefaultNodePoolArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterDefaultNodePool.html">output</a> API doc for this type.
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
            <td class="align-top">Availability<wbr>Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Auto<wbr>Scaling</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Node<wbr>Public<wbr>Ip</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Count</td>
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
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
            <td class="align-top">Node<wbr>Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Taints</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vm<wbr>Size</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vnet<wbr>Subnet<wbr>Id</td>
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
            <td class="align-top">Availability<wbr>Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Auto<wbr>Scaling</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Node<wbr>Public<wbr>Ip</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pods</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Count</td>
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
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
            <td class="align-top">Node<wbr>Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Node<wbr>Taints</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Os<wbr>Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vm<wbr>Size</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Vnet<wbr>Subnet<wbr>Id</td>
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
            <td class="align-top">availability<wbr>Zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Auto<wbr>Scaling</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Node<wbr>Public<wbr>Ip</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Pods</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Count</td>
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
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
            <td class="align-top">node<wbr>Labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node<wbr>Taints</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os<wbr>Disk<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vm<wbr>Size</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vnet<wbr>Subnet<wbr>Id</td>
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
            <td class="align-top">availability_<wbr>zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>auto_<wbr>scaling</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>node_<wbr>public_<wbr>ip</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>pods</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min_<wbr>count</td>
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
 (Required)
The name of the Managed Kubernetes Cluster to create. Changing this forces a new resource to be created.
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
            <td class="align-top">node_<wbr>labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">node_<wbr>taints</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">os_<wbr>disk_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vm_<wbr>size</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">vnet_<wbr>subnet_<wbr>id</td>
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





#### KubernetesClusterIdentity
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterIdentity">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterIdentity">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterIdentityArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterIdentityOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterIdentityArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterIdentity.html">output</a> API doc for this type.
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
            <td class="align-top">Principal<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The principal id of the system assigned identity which is used by master components.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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
            <td class="align-top">Principal<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The principal id of the system assigned identity which is used by master components.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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
            <td class="align-top">principal<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The principal id of the system assigned identity which is used by master components.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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
            <td class="align-top">principal_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The principal id of the system assigned identity which is used by master components.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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





#### KubernetesClusterKubeAdminConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterKubeAdminConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterKubeAdminConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterKubeAdminConfig.html">output</a> API doc for this type.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterKubeConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterKubeConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterKubeConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterKubeConfig.html">output</a> API doc for this type.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
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
Base64 encoded public certificate used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded private key used by clients to authenticate to the Kubernetes cluster.
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
Base64 encoded public CA certificate used as the root of trust for the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Kubernetes cluster server host.
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
A password or token used to authenticate to the Kubernetes cluster.
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
A username used to authenticate to the Kubernetes cluster.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterLinuxProfile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterLinuxProfile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterLinuxProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterLinuxProfileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterLinuxProfileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterLinuxProfileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterLinuxProfile.html">output</a> API doc for this type.
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
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssh<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofilesshkey">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile<wbr>Ssh<wbr>Key<wbr>Args</a></code>
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
            <td class="align-top">Admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssh<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofilesshkey">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile<wbr>Ssh<wbr>Key</a></code>
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
            <td class="align-top">admin<wbr>Username</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssh<wbr>Key</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofilesshkey">Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile<wbr>Ssh<wbr>Key</a></code>
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
            <td class="align-top">admin_<wbr>username</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssh_<wbr>key</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterlinuxprofilesshkey">Dict[Kubernetes<wbr>Cluster<wbr>Linux<wbr>Profile<wbr>Ssh<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterLinuxProfileSshKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterLinuxProfileSshKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterLinuxProfileSshKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterLinuxProfileSshKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterLinuxProfileSshKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterLinuxProfileSshKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterLinuxProfileSshKey.html">output</a> API doc for this type.
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
            <td class="align-top">Key<wbr>Data</td>
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
            <td class="align-top">Key<wbr>Data</td>
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
            <td class="align-top">key<wbr>Data</td>
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
            <td class="align-top">key<wbr>Data</td>
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





#### KubernetesClusterNetworkProfile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterNetworkProfile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterNetworkProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterNetworkProfileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterNetworkProfileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterNetworkProfileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterNetworkProfile.html">output</a> API doc for this type.
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
            <td class="align-top">Dns<wbr>Service<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Docker<wbr>Bridge<wbr>Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofileloadbalancerprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile<wbr>Load<wbr>Balancer<wbr>Profile<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Sku</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Plugin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Cidr</td>
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
            <td class="align-top">Dns<wbr>Service<wbr>Ip</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Docker<wbr>Bridge<wbr>Cidr</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofileloadbalancerprofile">*Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile<wbr>Load<wbr>Balancer<wbr>Profile</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancer<wbr>Sku</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Plugin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Network<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pod<wbr>Cidr</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Cidr</td>
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
            <td class="align-top">dns<wbr>Service<wbr>Ip</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">docker<wbr>Bridge<wbr>Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofileloadbalancerprofile">Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile<wbr>Load<wbr>Balancer<wbr>Profile?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Sku</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Plugin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod<wbr>Cidr</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Cidr</td>
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
            <td class="align-top">dns<wbr>Service<wbr>Ip</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">docker<wbr>Bridge<wbr>Cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Profile</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusternetworkprofileloadbalancerprofile">Dict[Kubernetes<wbr>Cluster<wbr>Network<wbr>Profile<wbr>Load<wbr>Balancer<wbr>Profile]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancer<wbr>Sku</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Plugin</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">network<wbr>Policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pod<wbr>Cidr</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Cidr</td>
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





#### KubernetesClusterNetworkProfileLoadBalancerProfile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterNetworkProfileLoadBalancerProfile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterNetworkProfileLoadBalancerProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterNetworkProfileLoadBalancerProfileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterNetworkProfileLoadBalancerProfileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterNetworkProfileLoadBalancerProfileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterNetworkProfileLoadBalancerProfile.html">output</a> API doc for this type.
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
            <td class="align-top">Effective<wbr>Outbound<wbr>Ips</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The outcome (resource IDs) of the specified arguments.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Managed<wbr>Outbound<wbr>Ip<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Outbound<wbr>Ip<wbr>Address<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Outbound<wbr>Ip<wbr>Prefix<wbr>Ids</td>
            <td class="align-top">
                
                <code>List<string>?</code>
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
            <td class="align-top">Effective<wbr>Outbound<wbr>Ips</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The outcome (resource IDs) of the specified arguments.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Managed<wbr>Outbound<wbr>Ip<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Outbound<wbr>Ip<wbr>Address<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Outbound<wbr>Ip<wbr>Prefix<wbr>Ids</td>
            <td class="align-top">
                
                <code>[]string</code>
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
            <td class="align-top">effective<wbr>Outbound<wbr>Ips</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The outcome (resource IDs) of the specified arguments.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">managed<wbr>Outbound<wbr>Ip<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">outbound<wbr>Ip<wbr>Address<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">outbound<wbr>Ip<wbr>Prefix<wbr>Ids</td>
            <td class="align-top">
                
                <code>string[]?</code>
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
            <td class="align-top">effective<wbr>Outbound<wbr>Ips</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The outcome (resource IDs) of the specified arguments.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">managed<wbr>Outbound<wbr>Ip<wbr>Count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">outbound<wbr>Ip<wbr>Address<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">outbound<wbr>Ip<wbr>Prefix<wbr>Ids</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterRoleBasedAccessControl
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterRoleBasedAccessControl">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterRoleBasedAccessControl">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterRoleBasedAccessControlArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterRoleBasedAccessControlOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterRoleBasedAccessControlArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterRoleBasedAccessControl.html">output</a> API doc for this type.
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
            <td class="align-top">Azure<wbr>Active<wbr>Directory</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrolazureactivedirectory">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control<wbr>Azure<wbr>Active<wbr>Directory<wbr>Args?</a></code>
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
            <td class="align-top">Azure<wbr>Active<wbr>Directory</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrolazureactivedirectory">*Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control<wbr>Azure<wbr>Active<wbr>Directory</a></code>
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
            <td class="align-top">azure<wbr>Active<wbr>Directory</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrolazureactivedirectory">Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control<wbr>Azure<wbr>Active<wbr>Directory?</a></code>
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
            <td class="align-top">azure_<wbr>active_<wbr>directory</td>
            <td class="align-top">
                
                <code><a href="#kubernetesclusterrolebasedaccesscontrolazureactivedirectory">Dict[Kubernetes<wbr>Cluster<wbr>Role<wbr>Based<wbr>Access<wbr>Control<wbr>Azure<wbr>Active<wbr>Directory]</a></code>
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
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterRoleBasedAccessControlAzureActiveDirectory
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterRoleBasedAccessControlAzureActiveDirectory">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterRoleBasedAccessControlAzureActiveDirectory">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterRoleBasedAccessControlAzureActiveDirectoryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterRoleBasedAccessControlAzureActiveDirectoryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterRoleBasedAccessControlAzureActiveDirectoryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterRoleBasedAccessControlAzureActiveDirectory.html">output</a> API doc for this type.
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
            <td class="align-top">Client<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Server<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Server<wbr>App<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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
            <td class="align-top">Client<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Server<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Server<wbr>App<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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
            <td class="align-top">client<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">server<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">server<wbr>App<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
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
            <td class="align-top">client<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">server<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">server<wbr>App<wbr>Secret</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The tenant id of the system assigned identity which is used by master components.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### KubernetesClusterServicePrincipal
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterServicePrincipal">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterServicePrincipal">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterServicePrincipalArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterServicePrincipalOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterServicePrincipalArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterServicePrincipal.html">output</a> API doc for this type.
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
            <td class="align-top">Client<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Client<wbr>Secret</td>
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
            <td class="align-top">Client<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Client<wbr>Secret</td>
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
            <td class="align-top">client<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">client<wbr>Secret</td>
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
            <td class="align-top">client_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">client_<wbr>secret</td>
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





#### KubernetesClusterWindowsProfile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#KubernetesClusterWindowsProfile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#KubernetesClusterWindowsProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterWindowsProfileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/containerservice?tab=doc#KubernetesClusterWindowsProfileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterWindowsProfileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Containerservice.KubernetesClusterWindowsProfile.html">output</a> API doc for this type.
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
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
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
            <td class="align-top">Admin<wbr>Password</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Username</td>
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
            <td class="align-top">admin<wbr>Password</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Username</td>
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
            <td class="align-top">admin_<wbr>password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin_<wbr>username</td>
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








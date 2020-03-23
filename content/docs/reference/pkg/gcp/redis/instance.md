
---
title: "Instance"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Instance Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/redis/#Instance">Instance</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/redis/#InstanceArgs">InstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Instance</span><span class="p">(resource_name, opts=None, </span>alternative_location_id=None<span class="p">, </span>authorized_network=None<span class="p">, </span>display_name=None<span class="p">, </span>labels=None<span class="p">, </span>location_id=None<span class="p">, </span>memory_size_gb=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>redis_configs=None<span class="p">, </span>redis_version=None<span class="p">, </span>region=None<span class="p">, </span>reserved_ip_range=None<span class="p">, </span>tier=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/redis?tab=doc#InstanceArgs">InstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/redis?tab=doc#Instance">Instance</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Redis.Instance.html">Instance</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Redis.InstanceArgs.html">InstanceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Instance resource with the given unique name, arguments, and options.

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
            <td class="align-top">Alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
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
An arbitrary and optional user-provided name for the instance.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
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
            <td class="align-top">Redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">Alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
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
An arbitrary and optional user-provided name for the instance.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
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
            <td class="align-top">Redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redis<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
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
An arbitrary and optional user-provided name for the instance.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
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
            <td class="align-top">redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">alternative_<wbr>location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authorized_<wbr>network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
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
An arbitrary and optional user-provided name for the instance.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">memory_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
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
            <td class="align-top">redis_<wbr>configs</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redis_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reserved_<wbr>ip_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Instance Output Properties

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
            <td class="align-top">Alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Current<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An arbitrary and optional user-provided name for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Redis memory size in GiB.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The port number of the exposed Redis endpoint.
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
            <td class="align-top">Redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">Alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Current<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An arbitrary and optional user-provided name for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} Redis memory size in GiB.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The port number of the exposed Redis endpoint.
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
            <td class="align-top">Redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">current<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An arbitrary and optional user-provided name for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} Redis memory size in GiB.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The port number of the exposed Redis endpoint.
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
            <td class="align-top">redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">alternative_<wbr>location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authorized_<wbr>network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">current_<wbr>location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An arbitrary and optional user-provided name for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">memory_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Redis memory size in GiB.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The port number of the exposed Redis endpoint.
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
            <td class="align-top">redis_<wbr>configs</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redis_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reserved_<wbr>ip_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Instance Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/redis/#InstanceState">InstanceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/redis/#Instance">Instance</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>alternative_location_id=None<span class="p">, </span>authorized_network=None<span class="p">, </span>create_time=None<span class="p">, </span>current_location_id=None<span class="p">, </span>display_name=None<span class="p">, </span>host=None<span class="p">, </span>labels=None<span class="p">, </span>location_id=None<span class="p">, </span>memory_size_gb=None<span class="p">, </span>name=None<span class="p">, </span>port=None<span class="p">, </span>project=None<span class="p">, </span>redis_configs=None<span class="p">, </span>redis_version=None<span class="p">, </span>region=None<span class="p">, </span>reserved_ip_range=None<span class="p">, </span>tier=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/redis?tab=doc#InstanceState">InstanceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/redis?tab=doc#Instance">Instance</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Redis.Instance.html">Instance</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Redis.InstanceState.html">InstanceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Instance resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Current<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
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
An arbitrary and optional user-provided name for the instance.
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
Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The port number of the exposed Redis endpoint.
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
            <td class="align-top">Redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">Alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Current<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
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
An arbitrary and optional user-provided name for the instance.
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
Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The port number of the exposed Redis endpoint.
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
            <td class="align-top">Redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redis<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">alternative<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authorized<wbr>Network</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">current<wbr>Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
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
An arbitrary and optional user-provided name for the instance.
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
Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">memory<wbr>Size<wbr>Gb</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The port number of the exposed Redis endpoint.
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
            <td class="align-top">redis<wbr>Configs</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redis<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reserved<wbr>Ip<wbr>Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
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
            <td class="align-top">alternative_<wbr>location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Only applicable to STANDARD_HA tier which protects the instance against zonal failures by provisioning it across two
zones. If provided, it must be a different zone from the one provided in [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authorized_<wbr>network</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The full name of the Google Compute Engine network to which the instance is connected. If left unspecified, the default
network will be used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time the instance was created in RFC3339 UTC &#34;Zulu&#34; format, accurate to nanoseconds.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">current_<wbr>location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current zone where the Redis endpoint is placed. For Basic Tier instances, this will always be the same as the
[locationId] provided by the user at creation time. For Standard Tier instances, this can be either [locationId] or
[alternativeLocationId] and can change after a failover event.
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
An arbitrary and optional user-provided name for the instance.
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
Hostname or IP address of the exposed Redis endpoint used by clients to connect to the service.
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
Resource labels to represent user provided metadata.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The zone where the instance will be provisioned. If not provided, the service will choose a zone for the instance. For
STANDARD_HA tier, instances will be created across two zones for protection against zonal failures. If
[alternativeLocationId] is also provided, it must be different from [locationId].
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">memory_<wbr>size_<wbr>gb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis memory size in GiB.
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
The ID of the instance or a fully qualified identifier for the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The port number of the exposed Redis endpoint.
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
            <td class="align-top">redis_<wbr>configs</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Redis configuration parameters, according to http://redis.io/topics/config. Please check Memorystore documentation for
the list of supported parameters:
https://cloud.google.com/memorystore/docs/redis/reference/rest/v1/projects.locations.instances#Instance.FIELDS.redis_configs
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redis_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of Redis software. If not provided, latest supported version will be used. Currently, the supported values
are: - REDIS_4_0 for Redis 4.0 compatibility - REDIS_3_2 for Redis 3.2 compatibility
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
The name of the Redis region of the instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reserved_<wbr>ip_<wbr>range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The CIDR range of internal addresses that are reserved for this instance. If not provided, the service will choose an
unused /29 block, for example, 10.0.0.0/29 or 192.168.0.0/29. Ranges must be unique and non-overlapping with existing
subnets in an authorized network.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The service tier of the instance. Must be one of these values: - BASIC: standalone instance - STANDARD_HA: highly
available primary/replica instances
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










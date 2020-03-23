
---
title: "BackendService"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a BackendService Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendService">BackendService</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendServiceArgs">BackendServiceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BackendService</span><span class="p">(resource_name, opts=None, </span>affinity_cookie_ttl_sec=None<span class="p">, </span>backends=None<span class="p">, </span>cdn_policy=None<span class="p">, </span>circuit_breakers=None<span class="p">, </span>connection_draining_timeout_sec=None<span class="p">, </span>consistent_hash=None<span class="p">, </span>custom_request_headers=None<span class="p">, </span>description=None<span class="p">, </span>enable_cdn=None<span class="p">, </span>health_checks=None<span class="p">, </span>iap=None<span class="p">, </span>load_balancing_scheme=None<span class="p">, </span>locality_lb_policy=None<span class="p">, </span>log_config=None<span class="p">, </span>name=None<span class="p">, </span>outlier_detection=None<span class="p">, </span>port_name=None<span class="p">, </span>project=None<span class="p">, </span>protocol=None<span class="p">, </span>security_policy=None<span class="p">, </span>session_affinity=None<span class="p">, </span>timeout_sec=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBackendService<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceArgs">BackendServiceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendService">BackendService</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendService.html">BackendService</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceArgs.html">BackendServiceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a BackendService resource with the given unique name, arguments, and options.

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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">List&lt;Backend<wbr>Service<wbr>Backend<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Backend<wbr>Service<wbr>Circuit<wbr>Breakers<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Backend<wbr>Service<wbr>Iap<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">Outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">[]Backend<wbr>Service<wbr>Backend</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">*Backend<wbr>Service<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">*Backend<wbr>Service<wbr>Circuit<wbr>Breakers</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">*Backend<wbr>Service<wbr>Consistent<wbr>Hash</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">*Backend<wbr>Service<wbr>Iap</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">*Backend<wbr>Service<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">Outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">*Backend<wbr>Service<wbr>Outlier<wbr>Detection</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">Backend<wbr>Service<wbr>Backend[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Backend<wbr>Service<wbr>Circuit<wbr>Breakers?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Backend<wbr>Service<wbr>Consistent<wbr>Hash?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Backend<wbr>Service<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Backend<wbr>Service<wbr>Outlier<wbr>Detection?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">affinity_<wbr>cookie_<wbr>ttl_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">List[Backend<wbr>Service<wbr>Backend]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Dict[Backend<wbr>Service<wbr>Cdn<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">circuit_<wbr>breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Dict[Backend<wbr>Service<wbr>Circuit<wbr>Breakers]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection_<wbr>draining_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consistent_<wbr>hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Dict[Backend<wbr>Service<wbr>Consistent<wbr>Hash]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>request_<wbr>headers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health_<wbr>checks</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Dict[Backend<wbr>Service<wbr>Iap]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load_<wbr>balancing_<wbr>scheme</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">locality_<wbr>lb_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Dict[Backend<wbr>Service<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">outlier_<wbr>detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Dict[Backend<wbr>Service<wbr>Outlier<wbr>Detection]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">session_<wbr>affinity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## BackendService Output Properties

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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">List&lt;Backend<wbr>Service<wbr>Backend&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Backend<wbr>Service<wbr>Circuit<wbr>Breakers?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Backend<wbr>Service<wbr>Consistent<wbr>Hash?</a></code>
            </td>
            <td class="align-top">{{% md %}} Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">Custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Headers that the HTTP/S load balancer should add to proxied requests.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Backend<wbr>Service<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">Outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Backend<wbr>Service<wbr>Outlier<wbr>Detection?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">Session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">[]Backend<wbr>Service<wbr>Backend</a></code>
            </td>
            <td class="align-top">{{% md %}} The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">*Backend<wbr>Service<wbr>Circuit<wbr>Breakers</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">*Backend<wbr>Service<wbr>Consistent<wbr>Hash</a></code>
            </td>
            <td class="align-top">{{% md %}} Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">Custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Headers that the HTTP/S load balancer should add to proxied requests.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">*Backend<wbr>Service<wbr>Iap</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">Outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">*Backend<wbr>Service<wbr>Outlier<wbr>Detection</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">Session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">Backend<wbr>Service<wbr>Backend[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Backend<wbr>Service<wbr>Circuit<wbr>Breakers?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Backend<wbr>Service<wbr>Consistent<wbr>Hash?</a></code>
            </td>
            <td class="align-top">{{% md %}} Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Headers that the HTTP/S load balancer should add to proxied requests.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Cdn</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Backend<wbr>Service<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Backend<wbr>Service<wbr>Outlier<wbr>Detection?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">affinity_<wbr>cookie_<wbr>ttl_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">List[Backend<wbr>Service<wbr>Backend]</a></code>
            </td>
            <td class="align-top">{{% md %}} The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Dict[Backend<wbr>Service<wbr>Cdn<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">circuit_<wbr>breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Dict[Backend<wbr>Service<wbr>Circuit<wbr>Breakers]</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection_<wbr>draining_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consistent_<wbr>hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Dict[Backend<wbr>Service<wbr>Consistent<wbr>Hash]</a></code>
            </td>
            <td class="align-top">{{% md %}} Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">custom_<wbr>request_<wbr>headers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Headers that the HTTP/S load balancer should add to proxied requests.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An optional description of this resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>cdn</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, enable Cloud CDN for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">fingerprint</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health_<wbr>checks</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Dict[Backend<wbr>Service<wbr>Iap]</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load_<wbr>balancing_<wbr>scheme</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">locality_<wbr>lb_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Dict[Backend<wbr>Service<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">outlier_<wbr>detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Dict[Backend<wbr>Service<wbr>Outlier<wbr>Detection]</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The security policy associated with this backend service.
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
            <td class="align-top">session_<wbr>affinity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing BackendService Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendServiceState">BackendServiceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#BackendService">BackendService</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>affinity_cookie_ttl_sec=None<span class="p">, </span>backends=None<span class="p">, </span>cdn_policy=None<span class="p">, </span>circuit_breakers=None<span class="p">, </span>connection_draining_timeout_sec=None<span class="p">, </span>consistent_hash=None<span class="p">, </span>creation_timestamp=None<span class="p">, </span>custom_request_headers=None<span class="p">, </span>description=None<span class="p">, </span>enable_cdn=None<span class="p">, </span>fingerprint=None<span class="p">, </span>health_checks=None<span class="p">, </span>iap=None<span class="p">, </span>load_balancing_scheme=None<span class="p">, </span>locality_lb_policy=None<span class="p">, </span>log_config=None<span class="p">, </span>name=None<span class="p">, </span>outlier_detection=None<span class="p">, </span>port_name=None<span class="p">, </span>project=None<span class="p">, </span>protocol=None<span class="p">, </span>security_policy=None<span class="p">, </span>self_link=None<span class="p">, </span>session_affinity=None<span class="p">, </span>timeout_sec=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBackendService<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceState">BackendServiceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendService">BackendService</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendService.html">BackendService</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceState.html">BackendServiceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing BackendService resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">List&lt;Backend<wbr>Service<wbr>Backend<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Backend<wbr>Service<wbr>Circuit<wbr>Breakers<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">Custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
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
Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Backend<wbr>Service<wbr>Iap<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">Outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">Session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">[]Backend<wbr>Service<wbr>Backend</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">*Backend<wbr>Service<wbr>Cdn<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">*Backend<wbr>Service<wbr>Circuit<wbr>Breakers</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">*Backend<wbr>Service<wbr>Consistent<wbr>Hash</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">Custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
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
Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">*Backend<wbr>Service<wbr>Iap</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">*Backend<wbr>Service<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">Outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">*Backend<wbr>Service<wbr>Outlier<wbr>Detection</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">Session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">affinity<wbr>Cookie<wbr>Ttl<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">Backend<wbr>Service<wbr>Backend[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">circuit<wbr>Breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Backend<wbr>Service<wbr>Circuit<wbr>Breakers?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection<wbr>Draining<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consistent<wbr>Hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Backend<wbr>Service<wbr>Consistent<wbr>Hash?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">custom<wbr>Request<wbr>Headers</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
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
Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health<wbr>Checks</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Backend<wbr>Service<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load<wbr>Balancing<wbr>Scheme</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">locality<wbr>Lb<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Backend<wbr>Service<wbr>Log<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">outlier<wbr>Detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Backend<wbr>Service<wbr>Outlier<wbr>Detection?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">session<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
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
            <td class="align-top">affinity_<wbr>cookie_<wbr>ttl_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Lifetime of cookies in seconds if session_affinity is GENERATED_COOKIE. If set to 0, the cookie is non-persistent and
lasts only until the end of the browser session (or equivalent). The maximum allowed value for TTL is one day. When the
load balancing scheme is INTERNAL, this field is not used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backends</td>
            <td class="align-top">
                
                <code><a href="#backendservicebackend">List[Backend<wbr>Service<wbr>Backend]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of backends that serve this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cdn_<wbr>policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicy">Dict[Backend<wbr>Service<wbr>Cdn<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Cloud CDN configuration for this BackendService.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">circuit_<wbr>breakers</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakers">Dict[Backend<wbr>Service<wbr>Circuit<wbr>Breakers]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling the volume of connections to a backend service. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection_<wbr>draining_<wbr>timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time for which instance will be drained (not accept new connections, but still work to finish started).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consistent_<wbr>hash</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthash">Dict[Backend<wbr>Service<wbr>Consistent<wbr>Hash]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Consistent Hash-based load balancing can be used to provide soft session affinity based on HTTP headers, cookies or
other properties. This load balancing policy is applicable only for HTTP connections. The affinity to a particular
destination host will be lost when one or more hosts are added/removed from the destination service. This field
specifies parameters that control consistent hashing. This field only applies if the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED. This field is only applicable when locality_lb_policy is set to MAGLEV or RING_HASH.
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
            <td class="align-top">custom_<wbr>request_<wbr>headers</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Headers that the HTTP/S load balancer should add to proxied requests.
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
An optional description of this resource.
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
If true, enable Cloud CDN for this BackendService.
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
Fingerprint of this resource. A hash of the contents stored in this object. This field is used in optimistic locking.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">health_<wbr>checks</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The set of URLs to the HttpHealthCheck or HttpsHealthCheck resource for health checking this BackendService. Currently
at most one health check can be specified, and a health check is required. For internal load balancing, a URL to a
HealthCheck resource must be specified instead.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#backendserviceiap">Dict[Backend<wbr>Service<wbr>Iap]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">load_<wbr>balancing_<wbr>scheme</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Indicates whether the backend service will be used with internal or external load balancing. A backend service created
for one type of load balancing cannot be used with the other. Must be &#39;EXTERNAL&#39; or &#39;INTERNAL_SELF_MANAGED&#39; for a global
backend service. Defaults to &#39;EXTERNAL&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">locality_<wbr>lb_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The load balancing algorithm used within the scope of the locality. The possible values are - ROUND_ROBIN - This is a
simple policy in which each healthy backend is selected in round robin order. LEAST_REQUEST - An O(1) algorithm which
selects two random healthy hosts and picks the host which has fewer active requests. RING_HASH - The ring/modulo hash
load balancer implements consistent hashing to backends. The algorithm has the property that the addition/removal of a
host from a set of N hosts only affects 1/N of the requests. RANDOM - The load balancer selects a random healthy host.
ORIGINAL_DESTINATION - Backend host is selected based on the client connection metadata, i.e., connections are opened to
the same address as the destination address of the incoming connection before the connection was redirected to the load
balancer. MAGLEV - used as a drop in replacement for the ring hash load balancer. Maglev is not as stable as ring hash
but has faster table lookup build times and host selection times. For more information about Maglev, refer to
https://ai.google/research/pubs/pub44824 This field is applicable only when the load_balancing_scheme is set to
INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#backendservicelogconfig">Dict[Backend<wbr>Service<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
This field denotes the logging options for the load balancer traffic served by this backend service. If logging is
enabled, logs will be exported to Stackdriver.
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
            <td class="align-top">outlier_<wbr>detection</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetection">Dict[Backend<wbr>Service<wbr>Outlier<wbr>Detection]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings controlling eviction of unhealthy hosts from the load balancing pool. This field is applicable only when the
load_balancing_scheme is set to INTERNAL_SELF_MANAGED.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Name of backend port. The same name should appear in the instance groups referenced by this service. Required when the
load balancing scheme is EXTERNAL.
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
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The protocol this BackendService uses to communicate with backends. Possible values are HTTP, HTTPS, HTTP2, TCP, and
SSL. The default is HTTP. **NOTE**: HTTP2 is only valid for beta HTTP/2 load balancer types and may result in errors if
used with the GA API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The security policy associated with this backend service.
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
    
        <tr>
            <td class="align-top">session_<wbr>affinity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of session affinity to use. The default is NONE. Session affinity is not applicable if the protocol is UDP.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How many seconds to wait for the backend before considering it a failed request. Default is 30 seconds. Valid range is
[1, 86400].
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### BackendServiceBackend
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceBackend">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceBackend">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceBackendArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceBackendOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceBackendArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceBackend.html">output</a> API doc for this type.
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
            <td class="align-top">Balancing<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Capacity<wbr>Scaler</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Rate</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Rate<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Rate<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Utilization</td>
            <td class="align-top">
                
                <code>double?</code>
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
            <td class="align-top">Balancing<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Capacity<wbr>Scaler</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Rate</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Rate<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Rate<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Utilization</td>
            <td class="align-top">
                
                <code>*float64</code>
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
            <td class="align-top">balancing<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">capacity<wbr>Scaler</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Rate</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Rate<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Rate<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Utilization</td>
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
            <td class="align-top">balancing<wbr>Mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">capacity<wbr>Scaler</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Rate</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Rate<wbr>Per<wbr>Endpoint</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Rate<wbr>Per<wbr>Instance</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Utilization</td>
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





#### BackendServiceCdnPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceCdnPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceCdnPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCdnPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCdnPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCdnPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCdnPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Cache<wbr>Key<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicycachekeypolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy<wbr>Cache<wbr>Key<wbr>Policy<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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
            <td class="align-top">Cache<wbr>Key<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicycachekeypolicy">*Backend<wbr>Service<wbr>Cdn<wbr>Policy<wbr>Cache<wbr>Key<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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
            <td class="align-top">cache<wbr>Key<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicycachekeypolicy">Backend<wbr>Service<wbr>Cdn<wbr>Policy<wbr>Cache<wbr>Key<wbr>Policy?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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
            <td class="align-top">cache<wbr>Key<wbr>Policy</td>
            <td class="align-top">
                
                <code><a href="#backendservicecdnpolicycachekeypolicy">Dict[Backend<wbr>Service<wbr>Cdn<wbr>Policy<wbr>Cache<wbr>Key<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">signed<wbr>Url<wbr>Cache<wbr>Max<wbr>Age<wbr>Sec</td>
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





#### BackendServiceCdnPolicyCacheKeyPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceCdnPolicyCacheKeyPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceCdnPolicyCacheKeyPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCdnPolicyCacheKeyPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCdnPolicyCacheKeyPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCdnPolicyCacheKeyPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCdnPolicyCacheKeyPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Include<wbr>Host</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Protocol</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Query<wbr>String</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query<wbr>String<wbr>Blacklists</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query<wbr>String<wbr>Whitelists</td>
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
            <td class="align-top">Include<wbr>Host</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Protocol</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Query<wbr>String</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query<wbr>String<wbr>Blacklists</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query<wbr>String<wbr>Whitelists</td>
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
            <td class="align-top">include<wbr>Host</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Protocol</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Query<wbr>String</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query<wbr>String<wbr>Blacklists</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query<wbr>String<wbr>Whitelists</td>
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
            <td class="align-top">include<wbr>Host</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Protocol</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Query<wbr>String</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query<wbr>String<wbr>Blacklists</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query<wbr>String<wbr>Whitelists</td>
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





#### BackendServiceCircuitBreakers
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceCircuitBreakers">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceCircuitBreakers">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCircuitBreakersArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCircuitBreakersOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCircuitBreakersArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCircuitBreakers.html">output</a> API doc for this type.
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
            <td class="align-top">Connect<wbr>Timeout</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakersconnecttimeout">Backend<wbr>Service<wbr>Circuit<wbr>Breakers<wbr>Connect<wbr>Timeout<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pending<wbr>Requests</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Requests</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Requests<wbr>Per<wbr>Connection</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Retries</td>
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
            <td class="align-top">Connect<wbr>Timeout</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakersconnecttimeout">*Backend<wbr>Service<wbr>Circuit<wbr>Breakers<wbr>Connect<wbr>Timeout</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Connections</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Pending<wbr>Requests</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Requests</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Requests<wbr>Per<wbr>Connection</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Retries</td>
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
            <td class="align-top">connect<wbr>Timeout</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakersconnecttimeout">Backend<wbr>Service<wbr>Circuit<wbr>Breakers<wbr>Connect<wbr>Timeout?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Pending<wbr>Requests</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Requests</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Requests<wbr>Per<wbr>Connection</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Retries</td>
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
            <td class="align-top">connect<wbr>Timeout</td>
            <td class="align-top">
                
                <code><a href="#backendservicecircuitbreakersconnecttimeout">Dict[Backend<wbr>Service<wbr>Circuit<wbr>Breakers<wbr>Connect<wbr>Timeout]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Connections</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Pending<wbr>Requests</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Requests</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Requests<wbr>Per<wbr>Connection</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Retries</td>
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





#### BackendServiceCircuitBreakersConnectTimeout
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceCircuitBreakersConnectTimeout">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceCircuitBreakersConnectTimeout">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCircuitBreakersConnectTimeoutArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceCircuitBreakersConnectTimeoutOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCircuitBreakersConnectTimeoutArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceCircuitBreakersConnectTimeout.html">output</a> API doc for this type.
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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





#### BackendServiceConsistentHash
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceConsistentHash">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceConsistentHash">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceConsistentHashArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceConsistentHashOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceConsistentHashArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceConsistentHash.html">output</a> API doc for this type.
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
            <td class="align-top">Http<wbr>Cookie</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookie">Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Header<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimum<wbr>Ring<wbr>Size</td>
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
            <td class="align-top">Http<wbr>Cookie</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookie">*Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Header<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimum<wbr>Ring<wbr>Size</td>
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
            <td class="align-top">http<wbr>Cookie</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookie">Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Header<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimum<wbr>Ring<wbr>Size</td>
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
            <td class="align-top">http<wbr>Cookie</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookie">Dict[Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Header<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimum<wbr>Ring<wbr>Size</td>
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





#### BackendServiceConsistentHashHttpCookie
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceConsistentHashHttpCookie">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceConsistentHashHttpCookie">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceConsistentHashHttpCookieArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceConsistentHashHttpCookieOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceConsistentHashHttpCookieArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceConsistentHashHttpCookie.html">output</a> API doc for this type.
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
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ttl</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookiettl">Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie<wbr>Ttl<wbr>Args?</a></code>
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ttl</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookiettl">*Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie<wbr>Ttl</a></code>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ttl</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookiettl">Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie<wbr>Ttl?</a></code>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ttl</td>
            <td class="align-top">
                
                <code><a href="#backendserviceconsistenthashhttpcookiettl">Dict[Backend<wbr>Service<wbr>Consistent<wbr>Hash<wbr>Http<wbr>Cookie<wbr>Ttl]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### BackendServiceConsistentHashHttpCookieTtl
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceConsistentHashHttpCookieTtl">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceConsistentHashHttpCookieTtl">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceConsistentHashHttpCookieTtlArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceConsistentHashHttpCookieTtlOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceConsistentHashHttpCookieTtlArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceConsistentHashHttpCookieTtl.html">output</a> API doc for this type.
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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





#### BackendServiceIap
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceIap">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceIap">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceIapArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceIapOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceIapArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceIap.html">output</a> API doc for this type.
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
            <td class="align-top">Oauth2Client<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Client<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Client<wbr>Secret<wbr>Sha256</td>
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
            <td class="align-top">Oauth2Client<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Client<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Client<wbr>Secret<wbr>Sha256</td>
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
            <td class="align-top">oauth2Client<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Client<wbr>Secret</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Client<wbr>Secret<wbr>Sha256</td>
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
            <td class="align-top">oauth2Client<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Client<wbr>Secret</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Client<wbr>Secret<wbr>Sha256</td>
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





#### BackendServiceLogConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceLogConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceLogConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceLogConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceLogConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceLogConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceLogConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Enable</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sample<wbr>Rate</td>
            <td class="align-top">
                
                <code>double?</code>
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
            <td class="align-top">Enable</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sample<wbr>Rate</td>
            <td class="align-top">
                
                <code>*float64</code>
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
            <td class="align-top">enable</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sample<wbr>Rate</td>
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
            <td class="align-top">enable</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sample<wbr>Rate</td>
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





#### BackendServiceOutlierDetection
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceOutlierDetection">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceOutlierDetection">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceOutlierDetectionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceOutlierDetectionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceOutlierDetectionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceOutlierDetection.html">output</a> API doc for this type.
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
            <td class="align-top">Base<wbr>Ejection<wbr>Time</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectionbaseejectiontime">Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Base<wbr>Ejection<wbr>Time<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcing<wbr>Consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcing<wbr>Consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcing<wbr>Success<wbr>Rate</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interval</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectioninterval">Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Interval<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Ejection<wbr>Percent</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Success<wbr>Rate<wbr>Minimum<wbr>Hosts</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Success<wbr>Rate<wbr>Request<wbr>Volume</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Success<wbr>Rate<wbr>Stdev<wbr>Factor</td>
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
            <td class="align-top">Base<wbr>Ejection<wbr>Time</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectionbaseejectiontime">*Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Base<wbr>Ejection<wbr>Time</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcing<wbr>Consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcing<wbr>Consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcing<wbr>Success<wbr>Rate</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interval</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectioninterval">*Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Interval</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Ejection<wbr>Percent</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Success<wbr>Rate<wbr>Minimum<wbr>Hosts</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Success<wbr>Rate<wbr>Request<wbr>Volume</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Success<wbr>Rate<wbr>Stdev<wbr>Factor</td>
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
            <td class="align-top">base<wbr>Ejection<wbr>Time</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectionbaseejectiontime">Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Base<wbr>Ejection<wbr>Time?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcing<wbr>Consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcing<wbr>Consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcing<wbr>Success<wbr>Rate</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interval</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectioninterval">Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Interval?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Ejection<wbr>Percent</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">success<wbr>Rate<wbr>Minimum<wbr>Hosts</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">success<wbr>Rate<wbr>Request<wbr>Volume</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">success<wbr>Rate<wbr>Stdev<wbr>Factor</td>
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
            <td class="align-top">base<wbr>Ejection<wbr>Time</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectionbaseejectiontime">Dict[Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Base<wbr>Ejection<wbr>Time]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcing<wbr>Consecutive<wbr>Errors</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcing<wbr>Consecutive<wbr>Gateway<wbr>Failure</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcing<wbr>Success<wbr>Rate</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interval</td>
            <td class="align-top">
                
                <code><a href="#backendserviceoutlierdetectioninterval">Dict[Backend<wbr>Service<wbr>Outlier<wbr>Detection<wbr>Interval]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Ejection<wbr>Percent</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">success<wbr>Rate<wbr>Minimum<wbr>Hosts</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">success<wbr>Rate<wbr>Request<wbr>Volume</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">success<wbr>Rate<wbr>Stdev<wbr>Factor</td>
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





#### BackendServiceOutlierDetectionBaseEjectionTime
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceOutlierDetectionBaseEjectionTime">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceOutlierDetectionBaseEjectionTime">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceOutlierDetectionBaseEjectionTimeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceOutlierDetectionBaseEjectionTimeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceOutlierDetectionBaseEjectionTimeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceOutlierDetectionBaseEjectionTime.html">output</a> API doc for this type.
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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





#### BackendServiceOutlierDetectionInterval
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#BackendServiceOutlierDetectionInterval">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#BackendServiceOutlierDetectionInterval">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceOutlierDetectionIntervalArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#BackendServiceOutlierDetectionIntervalOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceOutlierDetectionIntervalArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.BackendServiceOutlierDetectionInterval.html">output</a> API doc for this type.
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">Nanos</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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
            <td class="align-top">nanos</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">seconds</td>
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








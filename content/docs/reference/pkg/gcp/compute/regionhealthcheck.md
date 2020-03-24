
---
title: "RegionHealthCheck"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Health Checks determine whether instances are responsive and able to do work.
They are an important part of a comprehensive load balancing configuration,
as they enable monitoring instances behind load balancers.

Health Checks poll instances at a specified interval. Instances that
do not respond successfully to some number of probes in a row are marked
as unhealthy. No new connections are sent to unhealthy instances,
though existing connections will continue. The health check will
continue to poll unhealthy instances. If an instance later responds
successfully to some number of consecutive probes, it is marked
healthy again and can receive new connections.


To get more information about RegionHealthCheck, see:

* [API documentation](https://cloud.google.com/compute/docs/reference/rest/beta/regionHealthChecks)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/load-balancing/docs/health-checks)

## Example Usage - Region Health Check Tcp


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const tcp_region_health_check = new gcp.compute.RegionHealthCheck("tcp-region-health-check", {
    checkIntervalSec: 1,
    tcpHealthCheck: {
        port: 80,
    },
    timeoutSec: 1,
});
```
## Example Usage - Region Health Check Tcp Full


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const tcp_region_health_check = new gcp.compute.RegionHealthCheck("tcp-region-health-check", {
    checkIntervalSec: 1,
    description: "Health check via tcp",
    healthyThreshold: 4,
    tcpHealthCheck: {
        portName: "health-check-port",
        portSpecification: "USE_NAMED_PORT",
        proxyHeader: "NONE",
        request: "ARE YOU HEALTHY?",
        response: "I AM HEALTHY",
    },
    timeoutSec: 1,
    unhealthyThreshold: 5,
});
```
## Example Usage - Region Health Check Ssl


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const ssl_region_health_check = new gcp.compute.RegionHealthCheck("ssl-region-health-check", {
    checkIntervalSec: 1,
    sslHealthCheck: {
        port: 443,
    },
    timeoutSec: 1,
});
```
## Example Usage - Region Health Check Ssl Full


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const ssl_region_health_check = new gcp.compute.RegionHealthCheck("ssl-region-health-check", {
    checkIntervalSec: 1,
    description: "Health check via ssl",
    healthyThreshold: 4,
    sslHealthCheck: {
        portName: "health-check-port",
        portSpecification: "USE_NAMED_PORT",
        proxyHeader: "NONE",
        request: "ARE YOU HEALTHY?",
        response: "I AM HEALTHY",
    },
    timeoutSec: 1,
    unhealthyThreshold: 5,
});
```
## Example Usage - Region Health Check Http


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const http_region_health_check = new gcp.compute.RegionHealthCheck("http-region-health-check", {
    checkIntervalSec: 1,
    httpHealthCheck: {
        port: 80,
    },
    timeoutSec: 1,
});
```
## Example Usage - Region Health Check Http Full


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const http_region_health_check = new gcp.compute.RegionHealthCheck("http-region-health-check", {
    checkIntervalSec: 1,
    description: "Health check via http",
    healthyThreshold: 4,
    httpHealthCheck: {
        host: "1.2.3.4",
        portName: "health-check-port",
        portSpecification: "USE_NAMED_PORT",
        proxyHeader: "NONE",
        requestPath: "/mypath",
        response: "I AM HEALTHY",
    },
    timeoutSec: 1,
    unhealthyThreshold: 5,
});
```
## Example Usage - Region Health Check Https


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const https_region_health_check = new gcp.compute.RegionHealthCheck("https-region-health-check", {
    checkIntervalSec: 1,
    httpsHealthCheck: {
        port: 443,
    },
    timeoutSec: 1,
});
```
## Example Usage - Region Health Check Https Full


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const https_region_health_check = new gcp.compute.RegionHealthCheck("https-region-health-check", {
    checkIntervalSec: 1,
    description: "Health check via https",
    healthyThreshold: 4,
    httpsHealthCheck: {
        host: "1.2.3.4",
        portName: "health-check-port",
        portSpecification: "USE_NAMED_PORT",
        proxyHeader: "NONE",
        requestPath: "/mypath",
        response: "I AM HEALTHY",
    },
    timeoutSec: 1,
    unhealthyThreshold: 5,
});
```
## Example Usage - Region Health Check Http2


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const http2_region_health_check = new gcp.compute.RegionHealthCheck("http2-region-health-check", {
    checkIntervalSec: 1,
    http2HealthCheck: {
        port: 443,
    },
    timeoutSec: 1,
});
```
## Example Usage - Region Health Check Http2 Full


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const http2_region_health_check = new gcp.compute.RegionHealthCheck("http2-region-health-check", {
    checkIntervalSec: 1,
    description: "Health check via http2",
    healthyThreshold: 4,
    http2HealthCheck: {
        host: "1.2.3.4",
        portName: "health-check-port",
        portSpecification: "USE_NAMED_PORT",
        proxyHeader: "NONE",
        requestPath: "/mypath",
        response: "I AM HEALTHY",
    },
    timeoutSec: 1,
    unhealthyThreshold: 5,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/compute_region_health_check.html.markdown.



## Create a RegionHealthCheck Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionHealthCheck">RegionHealthCheck</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionHealthCheckArgs">RegionHealthCheckArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">RegionHealthCheck</span><span class="p">(resource_name, opts=None, </span>check_interval_sec=None<span class="p">, </span>description=None<span class="p">, </span>healthy_threshold=None<span class="p">, </span>http2_health_check=None<span class="p">, </span>http_health_check=None<span class="p">, </span>https_health_check=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>ssl_health_check=None<span class="p">, </span>tcp_health_check=None<span class="p">, </span>timeout_sec=None<span class="p">, </span>unhealthy_threshold=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRegionHealthCheck<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckArgs">RegionHealthCheckArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheck">RegionHealthCheck</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheck.html">RegionHealthCheck</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckArgs.html">RegionHealthCheckArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a RegionHealthCheck resource with the given unique name, arguments, and options.

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
            <td class="align-top">Check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">Check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">*Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">*Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">*Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">*Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">*Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">check_<wbr>interval_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">healthy_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http2_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">https_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## RegionHealthCheck Output Properties

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
            <td class="align-top">Check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} How often (in seconds) to send a health check. The default value is 5 seconds.
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">Check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} How often (in seconds) to send a health check. The default value is 5 seconds.
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">*Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">*Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">*Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">*Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">*Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} How often (in seconds) to send a health check. The default value is 5 seconds.
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">check_<wbr>interval_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} How often (in seconds) to send a health check. The default value is 5 seconds.
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
            <td class="align-top">{{% md %}} An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">healthy_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http2_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">https_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">ssl_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing RegionHealthCheck Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionHealthCheckState">RegionHealthCheckState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#RegionHealthCheck">RegionHealthCheck</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>check_interval_sec=None<span class="p">, </span>creation_timestamp=None<span class="p">, </span>description=None<span class="p">, </span>healthy_threshold=None<span class="p">, </span>http2_health_check=None<span class="p">, </span>http_health_check=None<span class="p">, </span>https_health_check=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>region=None<span class="p">, </span>self_link=None<span class="p">, </span>ssl_health_check=None<span class="p">, </span>tcp_health_check=None<span class="p">, </span>timeout_sec=None<span class="p">, </span>type=None<span class="p">, </span>unhealthy_threshold=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRegionHealthCheck<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckState">RegionHealthCheckState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheck">RegionHealthCheck</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheck.html">RegionHealthCheck</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckState.html">RegionHealthCheckState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing RegionHealthCheck resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
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
The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">Check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">*Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">*Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">*Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">Ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">*Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">*Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
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
The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">check<wbr>Interval<wbr>Sec</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">healthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http2Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">https<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">ssl<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp<wbr>Health<wbr>Check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
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
The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy<wbr>Threshold</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
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
            <td class="align-top">check_<wbr>interval_<wbr>sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often (in seconds) to send a health check. The default value is 5 seconds.
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
An optional description of this resource. Provide this property when you create the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">healthy_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far unhealthy instance will be marked healthy after this many consecutive successes. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http2_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttp2healthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Http2Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttphealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Http<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">https_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthcheckhttpshealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Https<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Region in which the created health check should reside. If it is not provided, the provider region is used.
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
            <td class="align-top">ssl_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecksslhealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Ssl<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tcp_<wbr>health_<wbr>check</td>
            <td class="align-top">
                
                <code><a href="#regionhealthchecktcphealthcheck">Dict[Region<wbr>Health<wbr>Check<wbr>Tcp<wbr>Health<wbr>Check]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested object resource
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
How long (in seconds) to wait before claiming failure. The default value is 5 seconds. It is invalid for timeoutSec to
have greater value than checkIntervalSec.
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
The type of the health check. One of HTTP, HTTP2, HTTPS, TCP, or SSL.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy_<wbr>threshold</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A so-far healthy instance will be marked unhealthy after this many consecutive failures. The default value is 2.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### RegionHealthCheckHttp2HealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionHealthCheckHttp2HealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionHealthCheckHttp2HealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckHttp2HealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckHttp2HealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckHttp2HealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckHttp2HealthCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy_<wbr>header</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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





#### RegionHealthCheckHttpHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionHealthCheckHttpHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionHealthCheckHttpHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckHttpHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckHttpHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckHttpHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckHttpHealthCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy_<wbr>header</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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





#### RegionHealthCheckHttpsHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionHealthCheckHttpsHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionHealthCheckHttpsHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckHttpsHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckHttpsHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckHttpsHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckHttpsHealthCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">Host</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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
            <td class="align-top">host</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy_<wbr>header</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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





#### RegionHealthCheckSslHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionHealthCheckSslHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionHealthCheckSslHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckSslHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckSslHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckSslHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckSslHealthCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy_<wbr>header</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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





#### RegionHealthCheckTcpHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#RegionHealthCheckTcpHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#RegionHealthCheckTcpHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckTcpHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#RegionHealthCheckTcpHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckTcpHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.RegionHealthCheckTcpHealthCheck.html">output</a> API doc for this type.
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port<wbr>Specification</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response</td>
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy<wbr>Header</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port<wbr>Specification</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">proxy_<wbr>header</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response</td>
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








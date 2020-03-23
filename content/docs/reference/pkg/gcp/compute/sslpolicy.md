
---
title: "SSLPolicy"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a SSLPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SSLPolicy">SSLPolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SSLPolicyArgs">SSLPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SSLPolicy</span><span class="p">(resource_name, opts=None, </span>custom_features=None<span class="p">, </span>description=None<span class="p">, </span>min_tls_version=None<span class="p">, </span>name=None<span class="p">, </span>profile=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSSLPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SSLPolicyArgs">SSLPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SSLPolicy">SSLPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SSLPolicy.html">SSLPolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SSLPolicyArgs.html">SSLPolicyArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a SSLPolicy resource with the given unique name, arguments, and options.

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
            <td class="align-top">Custom<wbr>Features</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">Min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">Profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">Custom<wbr>Features</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">Min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">Profile</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">custom<wbr>Features</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">custom_<wbr>features</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">min_<wbr>tls_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">profile</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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







## SSLPolicy Output Properties

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
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Features</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">Enabled<wbr>Features</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The list of features enabled in the SSL policy.
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
            <td class="align-top">Min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">Profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">Creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Features</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">Enabled<wbr>Features</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The list of features enabled in the SSL policy.
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
            <td class="align-top">Min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">Profile</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">creation<wbr>Timestamp</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Features</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">enabled<wbr>Features</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The list of features enabled in the SSL policy.
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
            <td class="align-top">min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">creation_<wbr>timestamp</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Creation timestamp in RFC3339 text format.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>features</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">enabled_<wbr>features</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The list of features enabled in the SSL policy.
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
            <td class="align-top">min_<wbr>tls_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">profile</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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








## Look up an Existing SSLPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SSLPolicyState">SSLPolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SSLPolicy">SSLPolicy</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>creation_timestamp=None<span class="p">, </span>custom_features=None<span class="p">, </span>description=None<span class="p">, </span>enabled_features=None<span class="p">, </span>fingerprint=None<span class="p">, </span>min_tls_version=None<span class="p">, </span>name=None<span class="p">, </span>profile=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSSLPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SSLPolicyState">SSLPolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SSLPolicy">SSLPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SSLPolicy.html">SSLPolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SSLPolicyState.html">SSLPolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing SSLPolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Custom<wbr>Features</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">Enabled<wbr>Features</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of features enabled in the SSL policy.
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
            <td class="align-top">Min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">Profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">Custom<wbr>Features</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">Enabled<wbr>Features</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of features enabled in the SSL policy.
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
            <td class="align-top">Min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">Profile</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">custom<wbr>Features</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">enabled<wbr>Features</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of features enabled in the SSL policy.
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
            <td class="align-top">min<wbr>Tls<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">profile</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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
            <td class="align-top">custom_<wbr>features</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for which
ciphers are available to use. **Note**: this argument *must* be present when using the &#39;CUSTOM&#39; profile. This argument
*must not* be present when using any other profile.
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
            <td class="align-top">enabled_<wbr>features</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The list of features enabled in the SSL policy.
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
            <td class="align-top">min_<wbr>tls_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The minimum version of SSL protocol that can be used by the clients to establish a connection with the load balancer.
This can be one of &#39;TLS_1_0&#39;, &#39;TLS_1_1&#39;, &#39;TLS_1_2&#39;. Default is &#39;TLS_1_0&#39;.
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
            <td class="align-top">profile</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Profile specifies the set of SSL features that can be used by the load balancer when negotiating SSL with clients. This
can be one of &#39;COMPATIBLE&#39;, &#39;MODERN&#39;, &#39;RESTRICTED&#39;, or &#39;CUSTOM&#39;. If using &#39;CUSTOM&#39;, the set of SSL features to enable
must be specified in the &#39;customFeatures&#39; field. See the [official
documentation](https://cloud.google.com/compute/docs/load-balancing/ssl-policies#profilefeaturesupport) for information
on what cipher suites each profile provides. If &#39;CUSTOM&#39; is used, the &#39;custom_features&#39; attribute **must be set**.
Default is &#39;COMPATIBLE&#39;.
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










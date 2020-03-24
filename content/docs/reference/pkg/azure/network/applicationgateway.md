
---
title: "ApplicationGateway"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages an Application Gateway.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/application_gateway.html.markdown.



## Create a ApplicationGateway Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/network/#ApplicationGateway">ApplicationGateway</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/network/#ApplicationGatewayArgs">ApplicationGatewayArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ApplicationGateway</span><span class="p">(resource_name, opts=None, </span>authentication_certificates=None<span class="p">, </span>autoscale_configuration=None<span class="p">, </span>backend_address_pools=None<span class="p">, </span>backend_http_settings=None<span class="p">, </span>custom_error_configurations=None<span class="p">, </span>enable_http2=None<span class="p">, </span>frontend_ip_configurations=None<span class="p">, </span>frontend_ports=None<span class="p">, </span>gateway_ip_configurations=None<span class="p">, </span>http_listeners=None<span class="p">, </span>identity=None<span class="p">, </span>location=None<span class="p">, </span>name=None<span class="p">, </span>probes=None<span class="p">, </span>redirect_configurations=None<span class="p">, </span>request_routing_rules=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>rewrite_rule_sets=None<span class="p">, </span>sku=None<span class="p">, </span>ssl_certificates=None<span class="p">, </span>ssl_policies=None<span class="p">, </span>tags=None<span class="p">, </span>trusted_root_certificates=None<span class="p">, </span>url_path_maps=None<span class="p">, </span>waf_configuration=None<span class="p">, </span>zones=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewApplicationGateway<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayArgs">ApplicationGatewayArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGateway">ApplicationGateway</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGateway.html">ApplicationGateway</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayArgs.html">ApplicationGatewayArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ApplicationGateway resource with the given unique name, arguments, and options.

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
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">List&lt;Application<wbr>Gateway<wbr>Authentication<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">List&lt;Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">List&lt;Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">List&lt;Application<wbr>Gateway<wbr>Frontend<wbr>Port<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">List&lt;Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">List&lt;Application<wbr>Gateway<wbr>Http<wbr>Listener<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">List&lt;Application<wbr>Gateway<wbr>Probe<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">List&lt;Application<wbr>Gateway<wbr>Redirect<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">List&lt;Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">List&lt;Application<wbr>Gateway<wbr>Ssl<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">List&lt;Application<wbr>Gateway<wbr>Ssl<wbr>Policy<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">Trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">List&lt;Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">List&lt;Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">[]Application<wbr>Gateway<wbr>Authentication<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">*Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">[]Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">[]Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">[]Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">[]Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">[]Application<wbr>Gateway<wbr>Frontend<wbr>Port</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">[]Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">[]Application<wbr>Gateway<wbr>Http<wbr>Listener</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">*Application<wbr>Gateway<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">[]Application<wbr>Gateway<wbr>Probe</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">[]Application<wbr>Gateway<wbr>Redirect<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">[]Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">[]Application<wbr>Gateway<wbr>Ssl<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">[]Application<wbr>Gateway<wbr>Ssl<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">Trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">[]Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">[]Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">*Application<wbr>Gateway<wbr>Waf<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">Application<wbr>Gateway<wbr>Authentication<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">Application<wbr>Gateway<wbr>Frontend<wbr>Port[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">Application<wbr>Gateway<wbr>Http<wbr>Listener[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">Application<wbr>Gateway<wbr>Probe[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">Application<wbr>Gateway<wbr>Redirect<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">Application<wbr>Gateway<wbr>Ssl<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">Application<wbr>Gateway<wbr>Ssl<wbr>Policy[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Application<wbr>Gateway<wbr>Waf<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">authentication_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">List[Application<wbr>Gateway<wbr>Authentication<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscale_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Dict[Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>address_<wbr>pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">List[Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>http_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">List[Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>error_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">List[Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>http2</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">List[Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">List[Application<wbr>Gateway<wbr>Frontend<wbr>Port]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway_<wbr>ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">List[Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">List[Application<wbr>Gateway<wbr>Http<wbr>Listener]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Dict[Application<wbr>Gateway<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">List[Application<wbr>Gateway<wbr>Probe]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">List[Application<wbr>Gateway<wbr>Redirect<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request_<wbr>routing_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">List[Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite_<wbr>rule_<wbr>sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Dict[Application<wbr>Gateway<wbr>Sku]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">List[Application<wbr>Gateway<wbr>Ssl<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">List[Application<wbr>Gateway<wbr>Ssl<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">trusted_<wbr>root_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">List[Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url_<wbr>path_<wbr>maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">List[Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">waf_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Dict[Application<wbr>Gateway<wbr>Waf<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ApplicationGateway Output Properties

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
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">List&lt;Application<wbr>Gateway<wbr>Authentication<wbr>Certificate&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">List&lt;Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">List&lt;Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">List&lt;Application<wbr>Gateway<wbr>Frontend<wbr>Port&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">List&lt;Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">List&lt;Application<wbr>Gateway<wbr>Http<wbr>Listener&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">List&lt;Application<wbr>Gateway<wbr>Probe&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">List&lt;Application<wbr>Gateway<wbr>Redirect<wbr>Configuration&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">List&lt;Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `request_routing_rule` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku</a></code>
            </td>
            <td class="align-top">{{% md %}} A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">List&lt;Application<wbr>Gateway<wbr>Ssl<wbr>Certificate&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">List&lt;Application<wbr>Gateway<wbr>Ssl<wbr>Policy&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} a `ssl policy` block as defined below.
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
            <td class="align-top">Trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">List&lt;Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">List&lt;Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Application<wbr>Gateway<wbr>Waf<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">[]Application<wbr>Gateway<wbr>Authentication<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">*Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">[]Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">[]Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">[]Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">[]Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">[]Application<wbr>Gateway<wbr>Frontend<wbr>Port</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">[]Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">[]Application<wbr>Gateway<wbr>Http<wbr>Listener</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">[]Application<wbr>Gateway<wbr>Probe</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">[]Application<wbr>Gateway<wbr>Redirect<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">[]Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `request_routing_rule` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku</a></code>
            </td>
            <td class="align-top">{{% md %}} A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">[]Application<wbr>Gateway<wbr>Ssl<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">[]Application<wbr>Gateway<wbr>Ssl<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} a `ssl policy` block as defined below.
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
            <td class="align-top">Trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">[]Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">[]Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">*Application<wbr>Gateway<wbr>Waf<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">Application<wbr>Gateway<wbr>Authentication<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">Application<wbr>Gateway<wbr>Frontend<wbr>Port[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">Application<wbr>Gateway<wbr>Http<wbr>Listener[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">Application<wbr>Gateway<wbr>Probe[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">Application<wbr>Gateway<wbr>Redirect<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule[]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `request_routing_rule` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku</a></code>
            </td>
            <td class="align-top">{{% md %}} A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">Application<wbr>Gateway<wbr>Ssl<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">Application<wbr>Gateway<wbr>Ssl<wbr>Policy[]</a></code>
            </td>
            <td class="align-top">{{% md %}} a `ssl policy` block as defined below.
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
            <td class="align-top">trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Application<wbr>Gateway<wbr>Waf<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">authentication_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">List[Application<wbr>Gateway<wbr>Authentication<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscale_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Dict[Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>address_<wbr>pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">List[Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>http_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">List[Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>error_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">List[Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>http2</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">List[Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">List[Application<wbr>Gateway<wbr>Frontend<wbr>Port]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway_<wbr>ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">List[Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">List[Application<wbr>Gateway<wbr>Http<wbr>Listener]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Dict[Application<wbr>Gateway<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `identity` block.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">List[Application<wbr>Gateway<wbr>Probe]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">List[Application<wbr>Gateway<wbr>Redirect<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request_<wbr>routing_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">List[Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `request_routing_rule` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite_<wbr>rule_<wbr>sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Dict[Application<wbr>Gateway<wbr>Sku]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">List[Application<wbr>Gateway<wbr>Ssl<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">List[Application<wbr>Gateway<wbr>Ssl<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} a `ssl policy` block as defined below.
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
            <td class="align-top">trusted_<wbr>root_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">List[Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url_<wbr>path_<wbr>maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">List[Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">waf_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Dict[Application<wbr>Gateway<wbr>Waf<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A collection of availability zones to spread the Application Gateway over.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ApplicationGateway Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/network/#ApplicationGatewayState">ApplicationGatewayState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/network/#ApplicationGateway">ApplicationGateway</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>authentication_certificates=None<span class="p">, </span>autoscale_configuration=None<span class="p">, </span>backend_address_pools=None<span class="p">, </span>backend_http_settings=None<span class="p">, </span>custom_error_configurations=None<span class="p">, </span>enable_http2=None<span class="p">, </span>frontend_ip_configurations=None<span class="p">, </span>frontend_ports=None<span class="p">, </span>gateway_ip_configurations=None<span class="p">, </span>http_listeners=None<span class="p">, </span>identity=None<span class="p">, </span>location=None<span class="p">, </span>name=None<span class="p">, </span>probes=None<span class="p">, </span>redirect_configurations=None<span class="p">, </span>request_routing_rules=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>rewrite_rule_sets=None<span class="p">, </span>sku=None<span class="p">, </span>ssl_certificates=None<span class="p">, </span>ssl_policies=None<span class="p">, </span>tags=None<span class="p">, </span>trusted_root_certificates=None<span class="p">, </span>url_path_maps=None<span class="p">, </span>waf_configuration=None<span class="p">, </span>zones=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetApplicationGateway<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayState">ApplicationGatewayState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGateway">ApplicationGateway</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGateway.html">ApplicationGateway</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayState.html">ApplicationGatewayState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ApplicationGateway resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">List&lt;Application<wbr>Gateway<wbr>Authentication<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">List&lt;Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">List&lt;Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">List&lt;Application<wbr>Gateway<wbr>Frontend<wbr>Port<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">List&lt;Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">List&lt;Application<wbr>Gateway<wbr>Http<wbr>Listener<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">List&lt;Application<wbr>Gateway<wbr>Probe<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">List&lt;Application<wbr>Gateway<wbr>Redirect<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">List&lt;Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">List&lt;Application<wbr>Gateway<wbr>Ssl<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">List&lt;Application<wbr>Gateway<wbr>Ssl<wbr>Policy<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">Trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">List&lt;Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">List&lt;Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">[]Application<wbr>Gateway<wbr>Authentication<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">*Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">[]Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">[]Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">[]Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">[]Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">[]Application<wbr>Gateway<wbr>Frontend<wbr>Port</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">[]Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">[]Application<wbr>Gateway<wbr>Http<wbr>Listener</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">*Application<wbr>Gateway<wbr>Identity</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">[]Application<wbr>Gateway<wbr>Probe</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">[]Application<wbr>Gateway<wbr>Redirect<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">[]Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">*Application<wbr>Gateway<wbr>Sku</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">[]Application<wbr>Gateway<wbr>Ssl<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">[]Application<wbr>Gateway<wbr>Ssl<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">Trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">[]Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">[]Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">*Application<wbr>Gateway<wbr>Waf<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zones</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">Application<wbr>Gateway<wbr>Authentication<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscale<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable<wbr>Http2</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">Application<wbr>Gateway<wbr>Frontend<wbr>Port[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway<wbr>Ip<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">Application<wbr>Gateway<wbr>Http<wbr>Listener[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Application<wbr>Gateway<wbr>Identity?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">Application<wbr>Gateway<wbr>Probe[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">Application<wbr>Gateway<wbr>Redirect<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Routing<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Application<wbr>Gateway<wbr>Sku?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">Application<wbr>Gateway<wbr>Ssl<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">Application<wbr>Gateway<wbr>Ssl<wbr>Policy[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">trusted<wbr>Root<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">waf<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Application<wbr>Gateway<wbr>Waf<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
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
            <td class="align-top">authentication_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayauthenticationcertificate">List[Application<wbr>Gateway<wbr>Authentication<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">autoscale_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayautoscaleconfiguration">Dict[Application<wbr>Gateway<wbr>Autoscale<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `autoscale_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>address_<wbr>pools</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendaddresspool">List[Application<wbr>Gateway<wbr>Backend<wbr>Address<wbr>Pool]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_address_pool` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend_<wbr>http_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsetting">List[Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `backend_http_settings` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">custom_<wbr>error_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaycustomerrorconfiguration">List[Application<wbr>Gateway<wbr>Custom<wbr>Error<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enable_<wbr>http2</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is HTTP2 enabled on the application gateway resource? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendipconfiguration">List[Application<wbr>Gateway<wbr>Frontend<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ports</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayfrontendport">List[Application<wbr>Gateway<wbr>Frontend<wbr>Port]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `frontend_port` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gateway_<wbr>ip_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaygatewayipconfiguration">List[Application<wbr>Gateway<wbr>Gateway<wbr>Ip<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `gateway_ip_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http_<wbr>listeners</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistener">List[Application<wbr>Gateway<wbr>Http<wbr>Listener]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `http_listener` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identity</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayidentity">Dict[Application<wbr>Gateway<wbr>Identity]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `identity` block.
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
The Azure region where the Application Gateway should exist. Changing this forces a new resource to be created.
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probes</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobe">List[Application<wbr>Gateway<wbr>Probe]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `probe` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayredirectconfiguration">List[Application<wbr>Gateway<wbr>Redirect<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `redirect_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request_<wbr>routing_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrequestroutingrule">List[Application<wbr>Gateway<wbr>Request<wbr>Routing<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `request_routing_rule` blocks as defined below.
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
The name of the resource group in which to the Application Gateway should exist. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite_<wbr>rule_<wbr>sets</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriteruleset">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `rewrite_rule_set` blocks as defined below. Only valid for v2 SKUs.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sku</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysku">Dict[Application<wbr>Gateway<wbr>Sku]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `sku` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslcertificate">List[Application<wbr>Gateway<wbr>Ssl<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `ssl_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaysslpolicy">List[Application<wbr>Gateway<wbr>Ssl<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
a `ssl policy` block as defined below.
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
            <td class="align-top">trusted_<wbr>root_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaytrustedrootcertificate">List[Application<wbr>Gateway<wbr>Trusted<wbr>Root<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `trusted_root_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url_<wbr>path_<wbr>maps</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmap">List[Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `url_path_map` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">waf_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfiguration">Dict[Application<wbr>Gateway<wbr>Waf<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `waf_configuration` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zones</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of availability zones to spread the Application Gateway over.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ApplicationGatewayAuthenticationCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayAuthenticationCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayAuthenticationCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayAuthenticationCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayAuthenticationCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayAuthenticationCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayAuthenticationCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayAutoscaleConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayAutoscaleConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayAutoscaleConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayAutoscaleConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayAutoscaleConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayAutoscaleConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayAutoscaleConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Capacity</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Capacity</td>
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
            <td class="align-top">Max<wbr>Capacity</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Capacity</td>
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
            <td class="align-top">max<wbr>Capacity</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Capacity</td>
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
            <td class="align-top">max<wbr>Capacity</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Capacity</td>
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





#### ApplicationGatewayBackendAddressPool
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayBackendAddressPool">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayBackendAddressPool">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendAddressPoolArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendAddressPoolOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendAddressPoolArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendAddressPool.html">output</a> API doc for this type.
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
            <td class="align-top">Fqdns</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code>List<string>?</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Fqdns</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code>[]string</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">fqdns</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code>string[]?</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">fqdns</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ip<wbr>Addresses</td>
            <td class="align-top">
                
                <code>List[str]</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayBackendHttpSetting
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayBackendHttpSetting">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayBackendHttpSetting">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendHttpSettingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendHttpSettingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendHttpSettingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendHttpSetting.html">output</a> API doc for this type.
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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingauthenticationcertificate">List&lt;Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Authentication<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingconnectiondraining">Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Connection<wbr>Draining<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cookie<wbr>Based<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Address</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Probe.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probe<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Timeout</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trusted<wbr>Root<wbr>Certificate<wbr>Names</td>
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
            <td class="align-top">Affinity<wbr>Cookie<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingauthenticationcertificate">[]Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Authentication<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Connection<wbr>Draining</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingconnectiondraining">*Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Connection<wbr>Draining</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cookie<wbr>Based<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Address</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probe<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Probe.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Probe<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Timeout</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Trusted<wbr>Root<wbr>Certificate<wbr>Names</td>
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
            <td class="align-top">affinity<wbr>Cookie<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authentication<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingauthenticationcertificate">Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Authentication<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection<wbr>Draining</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingconnectiondraining">Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Connection<wbr>Draining?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cookie<wbr>Based<wbr>Affinity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Address</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probe<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Probe.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probe<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Timeout</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trusted<wbr>Root<wbr>Certificate<wbr>Names</td>
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
            <td class="align-top">affinity<wbr>Cookie<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">authentication_<wbr>certificates</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingauthenticationcertificate">List[Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Authentication<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `authentication_certificate` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">connection<wbr>Draining</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaybackendhttpsettingconnectiondraining">Dict[Application<wbr>Gateway<wbr>Backend<wbr>Http<wbr>Setting<wbr>Connection<wbr>Draining]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cookie<wbr>Based<wbr>Affinity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Address</td>
            <td class="align-top">
                
                <code>bool</code>
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
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probe_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Probe.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">probe<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Timeout</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">trusted<wbr>Root<wbr>Certificate<wbr>Names</td>
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





#### ApplicationGatewayBackendHttpSettingAuthenticationCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayBackendHttpSettingAuthenticationCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayBackendHttpSettingAuthenticationCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendHttpSettingAuthenticationCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendHttpSettingAuthenticationCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendHttpSettingAuthenticationCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendHttpSettingAuthenticationCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayBackendHttpSettingConnectionDraining
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayBackendHttpSettingConnectionDraining">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayBackendHttpSettingConnectionDraining">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendHttpSettingConnectionDrainingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayBackendHttpSettingConnectionDrainingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendHttpSettingConnectionDrainingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayBackendHttpSettingConnectionDraining.html">output</a> API doc for this type.
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
            <td class="align-top">Drain<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Drain<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">drain<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">drain<wbr>Timeout<wbr>Sec</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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





#### ApplicationGatewayCustomErrorConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayCustomErrorConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayCustomErrorConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayCustomErrorConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayCustomErrorConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayCustomErrorConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayCustomErrorConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status<wbr>Code</td>
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
            <td class="align-top">Custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status<wbr>Code</td>
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
            <td class="align-top">custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status<wbr>Code</td>
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
            <td class="align-top">custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status<wbr>Code</td>
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





#### ApplicationGatewayFrontendIpConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayFrontendIpConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayFrontendIpConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayFrontendIpConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayFrontendIpConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayFrontendIpConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayFrontendIpConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Address<wbr>Allocation</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ip<wbr>Address<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnet<wbr>Id</td>
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Private<wbr>Ip<wbr>Address<wbr>Allocation</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Ip<wbr>Address<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnet<wbr>Id</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Ip<wbr>Address</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Ip<wbr>Address<wbr>Allocation</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Ip<wbr>Address<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnet<wbr>Id</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private_<wbr>ip_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">private<wbr>Ip<wbr>Address<wbr>Allocation</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Ip<wbr>Address<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnet_<wbr>id</td>
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





#### ApplicationGatewayFrontendPort
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayFrontendPort">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayFrontendPort">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayFrontendPortArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayFrontendPortOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayFrontendPortArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayFrontendPort.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Port</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">port</td>
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





#### ApplicationGatewayGatewayIpConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayGatewayIpConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayGatewayIpConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayGatewayIpConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayGatewayIpConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayGatewayIpConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayGatewayIpConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnet<wbr>Id</td>
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Subnet<wbr>Id</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnet<wbr>Id</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">subnet_<wbr>id</td>
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





#### ApplicationGatewayHttpListener
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayHttpListener">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayHttpListener">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayHttpListenerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayHttpListenerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayHttpListenerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayHttpListener.html">output</a> API doc for this type.
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
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistenercustomerrorconfiguration">List&lt;Application<wbr>Gateway<wbr>Http<wbr>Listener<wbr>Custom<wbr>Error<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Port<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Port.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Sni</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificate<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated SSL Certificate.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificate<wbr>Name</td>
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
            <td class="align-top">Custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistenercustomerrorconfiguration">[]Application<wbr>Gateway<wbr>Http<wbr>Listener<wbr>Custom<wbr>Error<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Ip<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Port<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Port.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Frontend<wbr>Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Host<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Sni</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificate<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated SSL Certificate.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ssl<wbr>Certificate<wbr>Name</td>
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
            <td class="align-top">custom<wbr>Error<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistenercustomerrorconfiguration">Application<wbr>Gateway<wbr>Http<wbr>Listener<wbr>Custom<wbr>Error<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ip<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Ip<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Port<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Port.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Port<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Sni</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificate<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated SSL Certificate.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificate<wbr>Name</td>
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
            <td class="align-top">custom_<wbr>error_<wbr>configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayhttplistenercustomerrorconfiguration">List[Application<wbr>Gateway<wbr>Http<wbr>Listener<wbr>Custom<wbr>Error<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `custom_error_configuration` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ip_<wbr>configuration_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend_<wbr>ip_<wbr>configuration_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Port<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Frontend Port.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">frontend<wbr>Port<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">host_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Sni</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificate<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated SSL Certificate.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ssl<wbr>Certificate<wbr>Name</td>
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





#### ApplicationGatewayHttpListenerCustomErrorConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayHttpListenerCustomErrorConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayHttpListenerCustomErrorConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayHttpListenerCustomErrorConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayHttpListenerCustomErrorConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayHttpListenerCustomErrorConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayHttpListenerCustomErrorConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status<wbr>Code</td>
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
            <td class="align-top">Custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status<wbr>Code</td>
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
            <td class="align-top">custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status<wbr>Code</td>
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
            <td class="align-top">custom<wbr>Error<wbr>Page<wbr>Url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status<wbr>Code</td>
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





#### ApplicationGatewayIdentity
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayIdentity">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayIdentity">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayIdentityArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayIdentityOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayIdentityArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayIdentity.html">output</a> API doc for this type.
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
            <td class="align-top">Identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">identity<wbr>Ids</td>
            <td class="align-top">
                
                <code>str</code>
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
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayProbe
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayProbe">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayProbe">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayProbeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayProbeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayProbeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayProbe.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interval</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobematch">Application<wbr>Gateway<wbr>Probe<wbr>Match<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimum<wbr>Servers</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interval</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Match</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobematch">*Application<wbr>Gateway<wbr>Probe<wbr>Match</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Minimum<wbr>Servers</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Timeout</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unhealthy<wbr>Threshold</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interval</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobematch">Application<wbr>Gateway<wbr>Probe<wbr>Match?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimum<wbr>Servers</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy<wbr>Threshold</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interval</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">match</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayprobematch">Dict[Application<wbr>Gateway<wbr>Probe<wbr>Match]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">minimum<wbr>Servers</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pick<wbr>Host<wbr>Name<wbr>From<wbr>Backend<wbr>Http<wbr>Settings</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">protocol</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">timeout</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unhealthy<wbr>Threshold</td>
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





#### ApplicationGatewayProbeMatch
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayProbeMatch">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayProbeMatch">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayProbeMatchArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayProbeMatchOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayProbeMatchArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayProbeMatch.html">output</a> API doc for this type.
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
            <td class="align-top">Body</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status<wbr>Codes</td>
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
            <td class="align-top">Body</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Status<wbr>Codes</td>
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
            <td class="align-top">body</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status<wbr>Codes</td>
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
            <td class="align-top">body</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">status<wbr>Codes</td>
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





#### ApplicationGatewayRedirectConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRedirectConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRedirectConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRedirectConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRedirectConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRedirectConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRedirectConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Path</td>
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Url</td>
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Path</td>
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Url</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Path</td>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Url</td>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Path</td>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Url</td>
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





#### ApplicationGatewayRequestRoutingRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRequestRoutingRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRequestRoutingRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRequestRoutingRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRequestRoutingRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRequestRoutingRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRequestRoutingRule.html">output</a> API doc for this type.
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
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated HTTP Listener.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Map<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated URL Path Map.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Map<wbr>Name</td>
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
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated HTTP Listener.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Map<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated URL Path Map.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Path<wbr>Map<wbr>Name</td>
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
            <td class="align-top">backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated HTTP Listener.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Map<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated URL Path Map.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Map<wbr>Name</td>
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
            <td class="align-top">backend_<wbr>address_<wbr>pool_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listener<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated HTTP Listener.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Listener<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Map<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated URL Path Map.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Path<wbr>Map<wbr>Name</td>
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





#### ApplicationGatewayRewriteRuleSet
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRewriteRuleSet">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRewriteRuleSet">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSet.html">output</a> API doc for this type.
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterule">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Args&gt;?</a></code>
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
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterule">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule</a></code>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterule">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule[]?</a></code>
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
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterule">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayRewriteRuleSetRewriteRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRewriteRuleSetRewriteRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRewriteRuleSetRewriteRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRule.html">output</a> API doc for this type.
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
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulecondition">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Condition<wbr>Args&gt;?</a></code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulerequestheaderconfiguration">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Request<wbr>Header<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriteruleresponseheaderconfiguration">List&lt;Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Response<wbr>Header<wbr>Configuration<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Sequence</td>
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
            <td class="align-top">Conditions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulecondition">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Condition</a></code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulerequestheaderconfiguration">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Request<wbr>Header<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Response<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriteruleresponseheaderconfiguration">[]Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Response<wbr>Header<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Sequence</td>
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
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulecondition">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Condition[]?</a></code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulerequestheaderconfiguration">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Request<wbr>Header<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriteruleresponseheaderconfiguration">Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Response<wbr>Header<wbr>Configuration[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Sequence</td>
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
            <td class="align-top">conditions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulecondition">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Condition]</a></code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriterulerequestheaderconfiguration">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Request<wbr>Header<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">response<wbr>Header<wbr>Configurations</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayrewriterulesetrewriteruleresponseheaderconfiguration">List[Application<wbr>Gateway<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Rewrite<wbr>Rule<wbr>Response<wbr>Header<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Sequence</td>
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





#### ApplicationGatewayRewriteRuleSetRewriteRuleCondition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRewriteRuleSetRewriteRuleCondition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRewriteRuleSetRewriteRuleCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleConditionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleConditionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleConditionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleCondition.html">output</a> API doc for this type.
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
            <td class="align-top">Ignore<wbr>Case</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Negate</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pattern</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Variable</td>
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
            <td class="align-top">Ignore<wbr>Case</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Negate</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Pattern</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Variable</td>
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
            <td class="align-top">ignore<wbr>Case</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">negate</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pattern</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">variable</td>
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
            <td class="align-top">ignore<wbr>Case</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">negate</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">pattern</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">variable</td>
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





#### ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleRequestHeaderConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Header<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Header<wbr>Value</td>
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
            <td class="align-top">Header<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Header<wbr>Value</td>
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
            <td class="align-top">header<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">header<wbr>Value</td>
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
            <td class="align-top">header<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">header<wbr>Value</td>
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





#### ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayRewriteRuleSetRewriteRuleResponseHeaderConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Header<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Header<wbr>Value</td>
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
            <td class="align-top">Header<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Header<wbr>Value</td>
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
            <td class="align-top">header<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">header<wbr>Value</td>
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
            <td class="align-top">header<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">header<wbr>Value</td>
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





#### ApplicationGatewaySku
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewaySku">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewaySku">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewaySkuArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewaySkuOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewaySkuArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewaySku.html">output</a> API doc for this type.
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
            <td class="align-top">Capacity</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
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
            <td class="align-top">Capacity</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tier</td>
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
            <td class="align-top">capacity</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
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
            <td class="align-top">capacity</td>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tier</td>
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





#### ApplicationGatewaySslCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewaySslCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewaySslCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewaySslCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewaySslCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewaySslCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewaySslCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Vault<wbr>Secret<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Public<wbr>Cert<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Public Certificate Data associated with the SSL Certificate.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key<wbr>Vault<wbr>Secret<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Public<wbr>Cert<wbr>Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Public Certificate Data associated with the SSL Certificate.
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key<wbr>Vault<wbr>Secret<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">public<wbr>Cert<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Public Certificate Data associated with the SSL Certificate.
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key_<wbr>vault_<wbr>secret_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">public<wbr>Cert<wbr>Data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Public Certificate Data associated with the SSL Certificate.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewaySslPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewaySslPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewaySslPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewaySslPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewaySslPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewaySslPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewaySslPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Cipher<wbr>Suites</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled<wbr>Protocols</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Protocol<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Type</td>
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
            <td class="align-top">Cipher<wbr>Suites</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled<wbr>Protocols</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Protocol<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Type</td>
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
            <td class="align-top">cipher<wbr>Suites</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled<wbr>Protocols</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Protocol<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Type</td>
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
            <td class="align-top">cipher<wbr>Suites</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled<wbr>Protocols</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Protocol<wbr>Version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>type</td>
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





#### ApplicationGatewayTrustedRootCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayTrustedRootCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayTrustedRootCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayTrustedRootCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayTrustedRootCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayTrustedRootCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayTrustedRootCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
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
            <td class="align-top">data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayUrlPathMap
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayUrlPathMap">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayUrlPathMap">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayUrlPathMapArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayUrlPathMapOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayUrlPathMapArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayUrlPathMap.html">output</a> API doc for this type.
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
            <td class="align-top">Default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend HTTP Settings Collection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmappathrule">List&lt;Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map<wbr>Path<wbr>Rule<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of `path_rule` blocks as defined above.
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
            <td class="align-top">Default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend HTTP Settings Collection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Path<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmappathrule">[]Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map<wbr>Path<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of `path_rule` blocks as defined above.
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
            <td class="align-top">default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend HTTP Settings Collection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmappathrule">Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map<wbr>Path<wbr>Rule[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of `path_rule` blocks as defined above.
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
            <td class="align-top">default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Backend HTTP Settings Collection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Default Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">path<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewayurlpathmappathrule">List[Application<wbr>Gateway<wbr>Url<wbr>Path<wbr>Map<wbr>Path<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A list of `path_rule` blocks as defined above.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayUrlPathMapPathRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayUrlPathMapPathRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayUrlPathMapPathRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayUrlPathMapPathRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayUrlPathMapPathRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayUrlPathMapPathRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayUrlPathMapPathRule.html">output</a> API doc for this type.
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
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Paths</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
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
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Paths</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
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
            <td class="align-top">backend<wbr>Address<wbr>Pool<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">paths</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
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
            <td class="align-top">backend_<wbr>address_<wbr>pool_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend Address Pool.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Address<wbr>Pool<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Backend HTTP Settings Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">backend<wbr>Http<wbr>Settings<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the Rewrite Rule Set
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
The name of the Application Gateway. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">paths</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Redirect Configuration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Configuration<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID of the associated Rewrite Rule Set.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rewrite<wbr>Rule<wbr>Set<wbr>Name</td>
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





#### ApplicationGatewayWafConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayWafConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayWafConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayWafConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayWafConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayWafConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayWafConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Disabled<wbr>Rule<wbr>Groups</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationdisabledrulegroup">List&lt;Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Disabled<wbr>Rule<wbr>Group<wbr>Args&gt;?</a></code>
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
            <td class="align-top">Exclusions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationexclusion">List&lt;Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Exclusion<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">File<wbr>Upload<wbr>Limit<wbr>Mb</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Firewall<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Request<wbr>Body<wbr>Size<wbr>Kb</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Body<wbr>Check</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Set<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Set<wbr>Version</td>
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
            <td class="align-top">Disabled<wbr>Rule<wbr>Groups</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationdisabledrulegroup">[]Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Disabled<wbr>Rule<wbr>Group</a></code>
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
            <td class="align-top">Exclusions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationexclusion">[]Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Exclusion</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">File<wbr>Upload<wbr>Limit<wbr>Mb</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Firewall<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Request<wbr>Body<wbr>Size<wbr>Kb</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Request<wbr>Body<wbr>Check</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Set<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rule<wbr>Set<wbr>Version</td>
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
            <td class="align-top">disabled<wbr>Rule<wbr>Groups</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationdisabledrulegroup">Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Disabled<wbr>Rule<wbr>Group[]?</a></code>
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
            <td class="align-top">exclusions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationexclusion">Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Exclusion[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">file<wbr>Upload<wbr>Limit<wbr>Mb</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">firewall<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Request<wbr>Body<wbr>Size<wbr>Kb</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Body<wbr>Check</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Set<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Set<wbr>Version</td>
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
            <td class="align-top">disabled<wbr>Rule<wbr>Groups</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationdisabledrulegroup">List[Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Disabled<wbr>Rule<wbr>Group]</a></code>
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
            <td class="align-top">exclusions</td>
            <td class="align-top">
                
                <code><a href="#applicationgatewaywafconfigurationexclusion">List[Application<wbr>Gateway<wbr>Waf<wbr>Configuration<wbr>Exclusion]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">file<wbr>Upload<wbr>Limit<wbr>Mb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">firewall<wbr>Mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Request<wbr>Body<wbr>Size<wbr>Kb</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">request<wbr>Body<wbr>Check</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Set<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rule<wbr>Set<wbr>Version</td>
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





#### ApplicationGatewayWafConfigurationDisabledRuleGroup
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayWafConfigurationDisabledRuleGroup">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayWafConfigurationDisabledRuleGroup">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayWafConfigurationDisabledRuleGroupArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayWafConfigurationDisabledRuleGroupOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayWafConfigurationDisabledRuleGroupArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayWafConfigurationDisabledRuleGroup.html">output</a> API doc for this type.
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
            <td class="align-top">Rule<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rules</td>
            <td class="align-top">
                
                <code>List<int>?</code>
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
            <td class="align-top">Rule<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Rules</td>
            <td class="align-top">
                
                <code>[]int</code>
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
            <td class="align-top">rule<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rules</td>
            <td class="align-top">
                
                <code>number[]?</code>
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
            <td class="align-top">rule<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">rules</td>
            <td class="align-top">
                
                <code>List[Integer]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationGatewayWafConfigurationExclusion
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ApplicationGatewayWafConfigurationExclusion">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ApplicationGatewayWafConfigurationExclusion">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayWafConfigurationExclusionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/network?tab=doc#ApplicationGatewayWafConfigurationExclusionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayWafConfigurationExclusionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Network.ApplicationGatewayWafConfigurationExclusion.html">output</a> API doc for this type.
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
            <td class="align-top">Match<wbr>Variable</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selector</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selector<wbr>Match<wbr>Operator</td>
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
            <td class="align-top">Match<wbr>Variable</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selector</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Selector<wbr>Match<wbr>Operator</td>
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
            <td class="align-top">match<wbr>Variable</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selector</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selector<wbr>Match<wbr>Operator</td>
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
            <td class="align-top">match<wbr>Variable</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selector</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">selector<wbr>Match<wbr>Operator</td>
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









---
title: "SecurityScanConfig"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a SecurityScanConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SecurityScanConfig">SecurityScanConfig</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SecurityScanConfigArgs">SecurityScanConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SecurityScanConfig</span><span class="p">(resource_name, opts=None, </span>authentication=None<span class="p">, </span>blacklist_patterns=None<span class="p">, </span>display_name=None<span class="p">, </span>export_to_security_command_center=None<span class="p">, </span>max_qps=None<span class="p">, </span>project=None<span class="p">, </span>schedule=None<span class="p">, </span>starting_urls=None<span class="p">, </span>target_platforms=None<span class="p">, </span>user_agent=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSecurityScanConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigArgs">SecurityScanConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfig">SecurityScanConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfig.html">SecurityScanConfig</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigArgs.html">SecurityScanConfigArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a SecurityScanConfig resource with the given unique name, arguments, and options.

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
            <td class="align-top">Authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Qps</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Security<wbr>Scan<wbr>Config<wbr>Schedule<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Agent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
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
            <td class="align-top">Authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">*Security<wbr>Scan<wbr>Config<wbr>Authentication</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Qps</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">*Security<wbr>Scan<wbr>Config<wbr>Schedule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Agent</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
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
            <td class="align-top">authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Security<wbr>Scan<wbr>Config<wbr>Authentication?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Qps</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Security<wbr>Scan<wbr>Config<wbr>Schedule?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Agent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
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
            <td class="align-top">authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Dict[Security<wbr>Scan<wbr>Config<wbr>Authentication]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">blacklist_<wbr>patterns</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">export_<wbr>to_<wbr>security_<wbr>command_<wbr>center</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>qps</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Dict[Security<wbr>Scan<wbr>Config<wbr>Schedule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">starting_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>platforms</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>agent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## SecurityScanConfig Output Properties

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
            <td class="align-top">Authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Security<wbr>Scan<wbr>Config<wbr>Authentication?</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Qps</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Security<wbr>Scan<wbr>Config<wbr>Schedule?</a></code>
            </td>
            <td class="align-top">{{% md %}} The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Agent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Type of the user agents used for scanning
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
            <td class="align-top">Authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">*Security<wbr>Scan<wbr>Config<wbr>Authentication</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Qps</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">*Security<wbr>Scan<wbr>Config<wbr>Schedule</a></code>
            </td>
            <td class="align-top">{{% md %}} The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Agent</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Type of the user agents used for scanning
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
            <td class="align-top">authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Security<wbr>Scan<wbr>Config<wbr>Authentication?</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Qps</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Security<wbr>Scan<wbr>Config<wbr>Schedule?</a></code>
            </td>
            <td class="align-top">{{% md %}} The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Agent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Type of the user agents used for scanning
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
            <td class="align-top">authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Dict[Security<wbr>Scan<wbr>Config<wbr>Authentication]</a></code>
            </td>
            <td class="align-top">{{% md %}} The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">blacklist_<wbr>patterns</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">export_<wbr>to_<wbr>security_<wbr>command_<wbr>center</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>qps</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Dict[Security<wbr>Scan<wbr>Config<wbr>Schedule]</a></code>
            </td>
            <td class="align-top">{{% md %}} The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">starting_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>platforms</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>agent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Type of the user agents used for scanning
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing SecurityScanConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SecurityScanConfigState">SecurityScanConfigState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/compute/#SecurityScanConfig">SecurityScanConfig</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>authentication=None<span class="p">, </span>blacklist_patterns=None<span class="p">, </span>display_name=None<span class="p">, </span>export_to_security_command_center=None<span class="p">, </span>max_qps=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>schedule=None<span class="p">, </span>starting_urls=None<span class="p">, </span>target_platforms=None<span class="p">, </span>user_agent=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSecurityScanConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigState">SecurityScanConfigState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfig">SecurityScanConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfig.html">SecurityScanConfig</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigState.html">SecurityScanConfigState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing SecurityScanConfig resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
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
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Qps</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Security<wbr>Scan<wbr>Config<wbr>Schedule<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Agent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
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
            <td class="align-top">Authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">*Security<wbr>Scan<wbr>Config<wbr>Authentication</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
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
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Qps</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">*Security<wbr>Scan<wbr>Config<wbr>Schedule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Agent</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
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
            <td class="align-top">authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Security<wbr>Scan<wbr>Config<wbr>Authentication?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">blacklist<wbr>Patterns</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
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
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">export<wbr>To<wbr>Security<wbr>Command<wbr>Center</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Qps</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Security<wbr>Scan<wbr>Config<wbr>Schedule?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">starting<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target<wbr>Platforms</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Agent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
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
            <td class="align-top">authentication</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthentication">Dict[Security<wbr>Scan<wbr>Config<wbr>Authentication]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The authentication configuration. If specified, service will use the authentication configuration during scanning.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">blacklist_<wbr>patterns</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The blacklist URL patterns as described in https://cloud.google.com/security-scanner/docs/excluded-urls
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
The user provider display name of the ScanConfig.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">export_<wbr>to_<wbr>security_<wbr>command_<wbr>center</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls export of scan configurations and results to Cloud Security Command Center.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max_<wbr>qps</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively. Defaults to 15.
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
A server defined name for this index. Format: &#39;projects/{{project}}/scanConfigs/{{server_generated_id}}&#39;
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigschedule">Dict[Security<wbr>Scan<wbr>Config<wbr>Schedule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The schedule of the ScanConfig
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">starting_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The starting URLs from which the scanner finds site pages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target_<wbr>platforms</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>agent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Type of the user agents used for scanning
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### SecurityScanConfigAuthentication
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SecurityScanConfigAuthentication">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SecurityScanConfigAuthentication">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigAuthenticationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigAuthenticationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigAuthenticationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigAuthentication.html">output</a> API doc for this type.
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
            <td class="align-top">Custom<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationcustomaccount">Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Custom<wbr>Account<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationgoogleaccount">Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Google<wbr>Account<wbr>Args?</a></code>
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
            <td class="align-top">Custom<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationcustomaccount">*Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Custom<wbr>Account</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationgoogleaccount">*Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Google<wbr>Account</a></code>
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
            <td class="align-top">custom<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationcustomaccount">Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Custom<wbr>Account?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationgoogleaccount">Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Google<wbr>Account?</a></code>
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
            <td class="align-top">custom<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationcustomaccount">Dict[Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Custom<wbr>Account]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google<wbr>Account</td>
            <td class="align-top">
                
                <code><a href="#securityscanconfigauthenticationgoogleaccount">Dict[Security<wbr>Scan<wbr>Config<wbr>Authentication<wbr>Google<wbr>Account]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### SecurityScanConfigAuthenticationCustomAccount
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SecurityScanConfigAuthenticationCustomAccount">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SecurityScanConfigAuthenticationCustomAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigAuthenticationCustomAccountArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigAuthenticationCustomAccountOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigAuthenticationCustomAccountArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigAuthenticationCustomAccount.html">output</a> API doc for this type.
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
            <td class="align-top">Login<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">Login<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">login<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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
            <td class="align-top">login<wbr>Url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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





#### SecurityScanConfigAuthenticationGoogleAccount
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SecurityScanConfigAuthenticationGoogleAccount">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SecurityScanConfigAuthenticationGoogleAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigAuthenticationGoogleAccountArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigAuthenticationGoogleAccountOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigAuthenticationGoogleAccountArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigAuthenticationGoogleAccount.html">output</a> API doc for this type.
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
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Username</td>
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
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">username</td>
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





#### SecurityScanConfigSchedule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#SecurityScanConfigSchedule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#SecurityScanConfigSchedule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigScheduleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/compute?tab=doc#SecurityScanConfigScheduleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigScheduleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Compute.SecurityScanConfigSchedule.html">output</a> API doc for this type.
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
            <td class="align-top">Interval<wbr>Duration<wbr>Days</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule<wbr>Time</td>
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
            <td class="align-top">Interval<wbr>Duration<wbr>Days</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schedule<wbr>Time</td>
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
            <td class="align-top">interval<wbr>Duration<wbr>Days</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule<wbr>Time</td>
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
            <td class="align-top">interval<wbr>Duration<wbr>Days</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schedule<wbr>Time</td>
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








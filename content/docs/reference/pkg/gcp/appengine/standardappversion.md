
---
title: "StandardAppVersion"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Standard App Version resource to create a new version of standard GAE Application.
Currently supporting Zip and File Containers.
Currently does not support async operation checking.


To get more information about StandardAppVersion, see:

* [API documentation](https://cloud.google.com/appengine/docs/admin-api/reference/rest/v1/apps.services.versions)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/appengine/docs/admin-api/deploying-overview)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/app_engine_standard_app_version.html.markdown.



## Create a StandardAppVersion Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#StandardAppVersion">StandardAppVersion</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#StandardAppVersionArgs">StandardAppVersionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">StandardAppVersion</span><span class="p">(resource_name, opts=None, </span>delete_service_on_destroy=None<span class="p">, </span>deployment=None<span class="p">, </span>entrypoint=None<span class="p">, </span>env_variables=None<span class="p">, </span>handlers=None<span class="p">, </span>instance_class=None<span class="p">, </span>libraries=None<span class="p">, </span>noop_on_destroy=None<span class="p">, </span>project=None<span class="p">, </span>runtime=None<span class="p">, </span>runtime_api_version=None<span class="p">, </span>service=None<span class="p">, </span>threadsafe=None<span class="p">, </span>version_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewStandardAppVersion<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionArgs">StandardAppVersionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersion">StandardAppVersion</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersion.html">StandardAppVersion</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionArgs.html">StandardAppVersionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a StandardAppVersion resource with the given unique name, arguments, and options.

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
            <td class="align-top">Delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Standard<wbr>App<wbr>Version<wbr>Entrypoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Env<wbr>Variables</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">List&lt;Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">List&lt;Standard<wbr>App<wbr>Version<wbr>Library<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">Runtime</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threadsafe</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">Delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">*Standard<wbr>App<wbr>Version<wbr>Deployment</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">*Standard<wbr>App<wbr>Version<wbr>Entrypoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Env<wbr>Variables</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">[]Standard<wbr>App<wbr>Version<wbr>Handler</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">[]Standard<wbr>App<wbr>Version<wbr>Library</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">Runtime</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threadsafe</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Standard<wbr>App<wbr>Version<wbr>Deployment?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Standard<wbr>App<wbr>Version<wbr>Entrypoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">env<wbr>Variables</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">Standard<wbr>App<wbr>Version<wbr>Handler[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">Standard<wbr>App<wbr>Version<wbr>Library[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">runtime</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threadsafe</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">delete_<wbr>service_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Dict[Standard<wbr>App<wbr>Version<wbr>Deployment]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Dict[Standard<wbr>App<wbr>Version<wbr>Entrypoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">env_<wbr>variables</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">List[Standard<wbr>App<wbr>Version<wbr>Handler]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">List[Standard<wbr>App<wbr>Version<wbr>Library]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">noop_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">runtime</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runtime_<wbr>api_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threadsafe</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## StandardAppVersion Output Properties

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
            <td class="align-top">Delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Standard<wbr>App<wbr>Version<wbr>Deployment?</a></code>
            </td>
            <td class="align-top">{{% md %}} Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Standard<wbr>App<wbr>Version<wbr>Entrypoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Env<wbr>Variables</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">List&lt;Standard<wbr>App<wbr>Version<wbr>Handler&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">List&lt;Standard<wbr>App<wbr>Version<wbr>Library&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the application version will not be deleted.
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
            <td class="align-top">Runtime</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threadsafe</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">Delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">*Standard<wbr>App<wbr>Version<wbr>Deployment</a></code>
            </td>
            <td class="align-top">{{% md %}} Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">*Standard<wbr>App<wbr>Version<wbr>Entrypoint</a></code>
            </td>
            <td class="align-top">{{% md %}} The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Env<wbr>Variables</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">[]Standard<wbr>App<wbr>Version<wbr>Handler</a></code>
            </td>
            <td class="align-top">{{% md %}} An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">[]Standard<wbr>App<wbr>Version<wbr>Library</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the application version will not be deleted.
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
            <td class="align-top">Runtime</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threadsafe</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Standard<wbr>App<wbr>Version<wbr>Deployment?</a></code>
            </td>
            <td class="align-top">{{% md %}} Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Standard<wbr>App<wbr>Version<wbr>Entrypoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">env<wbr>Variables</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">Standard<wbr>App<wbr>Version<wbr>Handler[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">Standard<wbr>App<wbr>Version<wbr>Library[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the application version will not be deleted.
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
            <td class="align-top">runtime</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threadsafe</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">delete_<wbr>service_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Dict[Standard<wbr>App<wbr>Version<wbr>Deployment]</a></code>
            </td>
            <td class="align-top">{{% md %}} Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Dict[Standard<wbr>App<wbr>Version<wbr>Entrypoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">env_<wbr>variables</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">List[Standard<wbr>App<wbr>Version<wbr>Handler]</a></code>
            </td>
            <td class="align-top">{{% md %}} An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">List[Standard<wbr>App<wbr>Version<wbr>Library]</a></code>
            </td>
            <td class="align-top">{{% md %}} Configuration for third-party Python runtime libraries that are required by the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">noop_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, the application version will not be deleted.
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
            <td class="align-top">runtime</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runtime_<wbr>api_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threadsafe</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing StandardAppVersion Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#StandardAppVersionState">StandardAppVersionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#StandardAppVersion">StandardAppVersion</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>delete_service_on_destroy=None<span class="p">, </span>deployment=None<span class="p">, </span>entrypoint=None<span class="p">, </span>env_variables=None<span class="p">, </span>handlers=None<span class="p">, </span>instance_class=None<span class="p">, </span>libraries=None<span class="p">, </span>name=None<span class="p">, </span>noop_on_destroy=None<span class="p">, </span>project=None<span class="p">, </span>runtime=None<span class="p">, </span>runtime_api_version=None<span class="p">, </span>service=None<span class="p">, </span>threadsafe=None<span class="p">, </span>version_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetStandardAppVersion<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionState">StandardAppVersionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersion">StandardAppVersion</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersion.html">StandardAppVersion</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionState.html">StandardAppVersionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing StandardAppVersion resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Standard<wbr>App<wbr>Version<wbr>Entrypoint<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Env<wbr>Variables</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">List&lt;Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">List&lt;Standard<wbr>App<wbr>Version<wbr>Library<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
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
Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">Runtime</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threadsafe</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">Delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">*Standard<wbr>App<wbr>Version<wbr>Deployment</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">*Standard<wbr>App<wbr>Version<wbr>Entrypoint</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Env<wbr>Variables</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">[]Standard<wbr>App<wbr>Version<wbr>Handler</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Instance<wbr>Class</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">[]Standard<wbr>App<wbr>Version<wbr>Library</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
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
Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">Runtime</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Threadsafe</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">delete<wbr>Service<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Standard<wbr>App<wbr>Version<wbr>Deployment?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Standard<wbr>App<wbr>Version<wbr>Entrypoint?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">env<wbr>Variables</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">Standard<wbr>App<wbr>Version<wbr>Handler[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance<wbr>Class</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">Standard<wbr>App<wbr>Version<wbr>Library[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
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
Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">noop<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">runtime</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runtime<wbr>Api<wbr>Version</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threadsafe</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
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
            <td class="align-top">delete_<wbr>service_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the service will be deleted if it is the last version.    
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeployment">Dict[Standard<wbr>App<wbr>Version<wbr>Deployment]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Code and application artifacts that make up this version.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entrypoint</td>
            <td class="align-top">
                
                <code><a href="#standardappversionentrypoint">Dict[Standard<wbr>App<wbr>Version<wbr>Entrypoint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entrypoint for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">env_<wbr>variables</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Environment variables available to the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">handlers</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandler">List[Standard<wbr>App<wbr>Version<wbr>Handler]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An ordered list of URL-matching patterns that should be applied to incoming requests. The first matching URL handles the
request and other request handlers are not attempted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">instance_<wbr>class</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Instance class that is used to run this version. Valid values are AutomaticScaling F1, F2, F4, F4_1G (Only
AutomaticScaling is supported at the moment)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">libraries</td>
            <td class="align-top">
                
                <code><a href="#standardappversionlibrary">List[Standard<wbr>App<wbr>Version<wbr>Library]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configuration for third-party Python runtime libraries that are required by the application.
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
Full path to the Version resource in the API. Example, &#34;v1&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">noop_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, the application version will not be deleted.
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
            <td class="align-top">runtime</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Desired runtime. Example python27.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runtime_<wbr>api_<wbr>version</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The version of the API in the given runtime environment. Please see the app.yaml reference for valid values at
https://cloud.google.com/appengine/docs/standard//config/appref
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
AppEngine service resource
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">threadsafe</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether multiple requests can be dispatched to this version at once.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Relative name of the version within the service. For example, &#39;v1&#39;. Version names can contain only lowercase letters,
numbers, or hyphens. Reserved names,&#34;default&#34;, &#34;latest&#34;, and any name with the prefix &#34;ah-&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### StandardAppVersionDeployment
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionDeployment">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionDeployment">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionDeploymentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionDeploymentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionDeploymentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionDeployment.html">output</a> API doc for this type.
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
            <td class="align-top">Files</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentfile">List&lt;Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>File<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zip</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentzip">Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>Zip<wbr>Args?</a></code>
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
            <td class="align-top">Files</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentfile">[]Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>File</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Zip</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentzip">*Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>Zip</a></code>
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
            <td class="align-top">files</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentfile">Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>File[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zip</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentzip">Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>Zip?</a></code>
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
            <td class="align-top">files</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentfile">List[Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>File]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">zip</td>
            <td class="align-top">
                
                <code><a href="#standardappversiondeploymentzip">Dict[Standard<wbr>App<wbr>Version<wbr>Deployment<wbr>Zip]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### StandardAppVersionDeploymentFile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionDeploymentFile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionDeploymentFile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionDeploymentFileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionDeploymentFileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionDeploymentFileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionDeploymentFile.html">output</a> API doc for this type.
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha1Sum</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Url</td>
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sha1Sum</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Url</td>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha1Sum</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Url</td>
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sha1Sum</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Url</td>
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





#### StandardAppVersionDeploymentZip
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionDeploymentZip">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionDeploymentZip">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionDeploymentZipArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionDeploymentZipOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionDeploymentZipArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionDeploymentZip.html">output</a> API doc for this type.
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
            <td class="align-top">Files<wbr>Count</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Url</td>
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
            <td class="align-top">Files<wbr>Count</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Url</td>
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
            <td class="align-top">files<wbr>Count</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Url</td>
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
            <td class="align-top">files<wbr>Count</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Url</td>
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





#### StandardAppVersionEntrypoint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionEntrypoint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionEntrypoint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionEntrypointArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionEntrypointOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionEntrypointArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionEntrypoint.html">output</a> API doc for this type.
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
            <td class="align-top">Shell</td>
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
            <td class="align-top">Shell</td>
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
            <td class="align-top">shell</td>
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
            <td class="align-top">shell</td>
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





#### StandardAppVersionHandler
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionHandler">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionHandler">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionHandlerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionHandlerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionHandlerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionHandler.html">output</a> API doc for this type.
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
            <td class="align-top">Auth<wbr>Fail<wbr>Action</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Login</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Http<wbr>Response<wbr>Code</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Script</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerscript">Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Script<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Static<wbr>Files</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerstaticfiles">Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Static<wbr>Files<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Regex</td>
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
            <td class="align-top">Auth<wbr>Fail<wbr>Action</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Login</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Redirect<wbr>Http<wbr>Response<wbr>Code</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Script</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerscript">*Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Script</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Security<wbr>Level</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Static<wbr>Files</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerstaticfiles">*Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Static<wbr>Files</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Regex</td>
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
            <td class="align-top">auth<wbr>Fail<wbr>Action</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">login</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Http<wbr>Response<wbr>Code</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">script</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerscript">Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Script?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security<wbr>Level</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">static<wbr>Files</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerstaticfiles">Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Static<wbr>Files?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Regex</td>
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
            <td class="align-top">auth<wbr>Fail<wbr>Action</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">login</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">redirect<wbr>Http<wbr>Response<wbr>Code</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">script</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerscript">Dict[Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Script]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">security<wbr>Level</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">static<wbr>Files</td>
            <td class="align-top">
                
                <code><a href="#standardappversionhandlerstaticfiles">Dict[Standard<wbr>App<wbr>Version<wbr>Handler<wbr>Static<wbr>Files]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Regex</td>
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





#### StandardAppVersionHandlerScript
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionHandlerScript">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionHandlerScript">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionHandlerScriptArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionHandlerScriptOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionHandlerScriptArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionHandlerScript.html">output</a> API doc for this type.
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
            <td class="align-top">Script<wbr>Path</td>
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
            <td class="align-top">Script<wbr>Path</td>
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
            <td class="align-top">script<wbr>Path</td>
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
            <td class="align-top">script<wbr>Path</td>
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





#### StandardAppVersionHandlerStaticFiles
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionHandlerStaticFiles">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionHandlerStaticFiles">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionHandlerStaticFilesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionHandlerStaticFilesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionHandlerStaticFilesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionHandlerStaticFiles.html">output</a> API doc for this type.
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
            <td class="align-top">Application<wbr>Readable</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Headers</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mime<wbr>Type</td>
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
            <td class="align-top">Require<wbr>Matching<wbr>File</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upload<wbr>Path<wbr>Regex</td>
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
            <td class="align-top">Application<wbr>Readable</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Headers</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mime<wbr>Type</td>
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
            <td class="align-top">Require<wbr>Matching<wbr>File</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Upload<wbr>Path<wbr>Regex</td>
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
            <td class="align-top">application<wbr>Readable</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Headers</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mime<wbr>Type</td>
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
            <td class="align-top">require<wbr>Matching<wbr>File</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upload<wbr>Path<wbr>Regex</td>
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
            <td class="align-top">application<wbr>Readable</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Headers</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mime<wbr>Type</td>
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
            <td class="align-top">require<wbr>Matching<wbr>File</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">upload<wbr>Path<wbr>Regex</td>
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





#### StandardAppVersionLibrary
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#StandardAppVersionLibrary">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#StandardAppVersionLibrary">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionLibraryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#StandardAppVersionLibraryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionLibraryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.StandardAppVersionLibrary.html">output</a> API doc for this type.
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








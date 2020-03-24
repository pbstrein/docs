
---
title: "Application"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Allows creation and management of an App Engine application.

> App Engine applications cannot be deleted once they're created; you have to delete the
   entire project to delete the application. This provider will report the application has been
   successfully deleted; this is a limitation of the provider, and will go away in the future.
   This provider is not able to delete App Engine applications.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/app_engine_application.html.markdown.



## Create a Application Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#Application">Application</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#ApplicationArgs">ApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Application</span><span class="p">(resource_name, opts=None, </span>auth_domain=None<span class="p">, </span>feature_settings=None<span class="p">, </span>iap=None<span class="p">, </span>location_id=None<span class="p">, </span>project=None<span class="p">, </span>serving_status=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationArgs">ApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#Application">Application</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.Application.html">Application</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationArgs.html">ApplicationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Application resource with the given unique name, arguments, and options.

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
            <td class="align-top">Auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Application<wbr>Iap<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
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
            <td class="align-top">Auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">*Application<wbr>Feature<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">*Application<wbr>Iap</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Serving<wbr>Status</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
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
            <td class="align-top">auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Application<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
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
            <td class="align-top">auth_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">feature_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Dict[Application<wbr>Feature<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Dict[Application<wbr>Iap]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">serving_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Application Output Properties

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
            <td class="align-top">App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Code<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Hostname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gcr<wbr>Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Application<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique name of the app, usually `apps/{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Dispatch<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">List&lt;Application<wbr>Url<wbr>Dispatch<wbr>Rule&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
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
            <td class="align-top">App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Code<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Hostname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gcr<wbr>Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">*Application<wbr>Iap</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique name of the app, usually `apps/{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Dispatch<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">[]Application<wbr>Url<wbr>Dispatch<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
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
            <td class="align-top">app<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">code<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Hostname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gcr<wbr>Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Application<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique name of the app, usually `apps/{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Dispatch<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">Application<wbr>Url<wbr>Dispatch<wbr>Rule[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
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
            <td class="align-top">app_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">auth_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">code_<wbr>bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>hostname</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">feature_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Dict[Application<wbr>Feature<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}} A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gcr_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Dict[Application<wbr>Iap]</a></code>
            </td>
            <td class="align-top">{{% md %}} Settings for enabling Cloud Identity Aware Proxy
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Unique name of the app, usually `apps/{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">serving_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url_<wbr>dispatch_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">List[Application<wbr>Url<wbr>Dispatch<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Application Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#ApplicationState">ApplicationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/appengine/#Application">Application</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_id=None<span class="p">, </span>auth_domain=None<span class="p">, </span>code_bucket=None<span class="p">, </span>default_bucket=None<span class="p">, </span>default_hostname=None<span class="p">, </span>feature_settings=None<span class="p">, </span>gcr_domain=None<span class="p">, </span>iap=None<span class="p">, </span>location_id=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>serving_status=None<span class="p">, </span>url_dispatch_rules=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationState">ApplicationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#Application">Application</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.Application.html">Application</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationState.html">ApplicationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Application resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">App<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Code<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Hostname</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gcr<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Application<wbr>Iap<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
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
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
Unique name of the app, usually `apps/{PROJECT_ID}`
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Dispatch<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">List&lt;Application<wbr>Url<wbr>Dispatch<wbr>Rule<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
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
            <td class="align-top">App<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Code<wbr>Bucket</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Bucket</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Hostname</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">*Application<wbr>Feature<wbr>Settings</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Gcr<wbr>Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">*Application<wbr>Iap</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
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
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
Unique name of the app, usually `apps/{PROJECT_ID}`
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Serving<wbr>Status</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Url<wbr>Dispatch<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">[]Application<wbr>Url<wbr>Dispatch<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
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
            <td class="align-top">app<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">auth<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">code<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Hostname</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">feature<wbr>Settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Application<wbr>Feature<wbr>Settings?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gcr<wbr>Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Application<wbr>Iap?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
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
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
Unique name of the app, usually `apps/{PROJECT_ID}`
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">serving<wbr>Status</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url<wbr>Dispatch<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">Application<wbr>Url<wbr>Dispatch<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
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
            <td class="align-top">app_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Identifier of the app, usually `{PROJECT_ID}`
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">auth_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain to authenticate users with when using App Engine&#39;s User API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">code_<wbr>bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket code is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCS bucket content is being stored in for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>hostname</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default hostname for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">feature_<wbr>settings</td>
            <td class="align-top">
                
                <code><a href="#applicationfeaturesettings">Dict[Application<wbr>Feature<wbr>Settings]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A block of optional settings to configure specific App Engine features:
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">gcr_<wbr>domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The GCR domain used for storing managed Docker images for this app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">iap</td>
            <td class="align-top">
                
                <code><a href="#applicationiap">Dict[Application<wbr>Iap]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Settings for enabling Cloud Identity Aware Proxy
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
The [location](https://cloud.google.com/appengine/docs/locations)
to serve the app from.
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
Unique name of the app, usually `apps/{PROJECT_ID}`
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
The project ID to create the application under.
~&gt;**NOTE**: GCP only accepts project ID, not project number. If you are using number,
you may get a &#34;Permission denied&#34; error.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">serving_<wbr>status</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The serving status of the app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">url_<wbr>dispatch_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#applicationurldispatchrule">List[Application<wbr>Url<wbr>Dispatch<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of dispatch rule blocks. Each block has a `domain`, `path`, and `service` field.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ApplicationFeatureSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ApplicationFeatureSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ApplicationFeatureSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationFeatureSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationFeatureSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationFeatureSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationFeatureSettings.html">output</a> API doc for this type.
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
            <td class="align-top">Split<wbr>Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Set to false to use the legacy health check instead of the readiness
and liveness checks.
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
            <td class="align-top">Split<wbr>Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Set to false to use the legacy health check instead of the readiness
and liveness checks.
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
            <td class="align-top">split<wbr>Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Set to false to use the legacy health check instead of the readiness
and liveness checks.
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
            <td class="align-top">split<wbr>Health<wbr>Checks</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Set to false to use the legacy health check instead of the readiness
and liveness checks.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationIap
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#ApplicationIap">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ApplicationIap">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationIapArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationIapOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationIapArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationIap.html">output</a> API doc for this type.
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





#### ApplicationUrlDispatchRule
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ApplicationUrlDispatchRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/appengine?tab=doc#ApplicationUrlDispatchRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Appengine.ApplicationUrlDispatchRule.html">output</a> API doc for this type.
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
            <td class="align-top">Domain</td>
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
            <td class="align-top">Service</td>
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
            <td class="align-top">Domain</td>
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
            <td class="align-top">Service</td>
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
            <td class="align-top">domain</td>
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
            <td class="align-top">service</td>
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
            <td class="align-top">domain</td>
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
            <td class="align-top">service</td>
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








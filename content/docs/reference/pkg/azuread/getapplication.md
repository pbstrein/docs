
---
title: "GetApplication"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Use this data source to access information about an existing Application within Azure Active Directory.

> **NOTE:** If you're authenticating using a Service Principal then it must have permissions to both `Read and write all (or owned by) applications` and `Sign in and read user profile` within the `Windows Azure Active Directory` API.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azuread/blob/master/website/docs/d/application.html.markdown.





## Using GetApplication

{{< langchoose csharp nojavascript >}}


<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getApplication<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#GetApplicationArgs">GetApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#GetApplicationResult">GetApplicationResult</a></span>></span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_application(</span>name=None<span class="p">, </span>oauth2_permissions=None<span class="p">, </span>object_id=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#GetApplicationArgs">GetApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#LookupApplicationResult">LookupApplicationResult</a></span>, error)</span></code></pre></div>


<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetApplication </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationResult.html">GetApplicationResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationArgs.html">GetApplicationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>



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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the name of the Application within Azure Active Directory.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">List&lt;Pulumi.<wbr>Azuread.<wbr>Get<wbr>Application<wbr>Oauth2Permission<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Object ID of the Application within Azure Active Directory.
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
Specifies the name of the Application within Azure Active Directory.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">[]Get<wbr>Application<wbr>Oauth2Permission</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Object ID of the Application within Azure Active Directory.
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
Specifies the name of the Application within Azure Active Directory.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">Get<wbr>Application<wbr>Oauth2Permission[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Object ID of the Application within Azure Active Directory.
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
Specifies the name of the Application within Azure Active Directory.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">List[Get<wbr>Application<wbr>Oauth2Permission]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the Object ID of the Application within Azure Active Directory.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## GetApplication Result

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
            <td class="align-top">App<wbr>Roles</td>
            <td class="align-top">
                
                <code><a href="#getapplicationapprole">List&lt;Pulumi.<wbr>Azuread.<wbr>Get<wbr>Application<wbr>App<wbr>Role&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Application<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} the Application ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The `groups` claim issued in a user or OAuth 2.0 access token that the app expects.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the logout page.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">List&lt;Pulumi.<wbr>Azuread.<wbr>Get<wbr>Application<wbr>Oauth2Permission&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} the Object ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of User Object IDs that are assigned ownership of the application registration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccess">List&lt;Pulumi.<wbr>Azuread.<wbr>Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the permission
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
            <td class="align-top">App<wbr>Roles</td>
            <td class="align-top">
                
                <code><a href="#getapplicationapprole">[]Get<wbr>Application<wbr>App<wbr>Role</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Application<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} the Application ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The `groups` claim issued in a user or OAuth 2.0 access token that the app expects.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the logout page.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">[]Get<wbr>Application<wbr>Oauth2Permission</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} the Object ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of User Object IDs that are assigned ownership of the application registration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccess">[]Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the permission
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
            <td class="align-top">app<wbr>Roles</td>
            <td class="align-top">
                
                <code><a href="#getapplicationapprole">Get<wbr>Application<wbr>App<wbr>Role[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">application<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} the Application ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The `groups` claim issued in a user or OAuth 2.0 access token that the app expects.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the logout page.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">Get<wbr>Application<wbr>Oauth2Permission[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} the Object ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of User Object IDs that are assigned ownership of the application registration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccess">Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access[]</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The type of the permission
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
            <td class="align-top">app_<wbr>roles</td>
            <td class="align-top">
                
                <code><a href="#getapplicationapprole">List[Get<wbr>Application<wbr>App<wbr>Role]</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">application_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} the Application ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available_<wbr>to_<wbr>other_<wbr>tenants</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group_<wbr>membership_<wbr>claims</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The `groups` claim issued in a user or OAuth 2.0 access token that the app expects.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} id is the provider-assigned unique ID for this managed resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identifier_<wbr>uris</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logout_<wbr>url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URL of the logout page.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>allow_<wbr>implicit_<wbr>flow</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens?
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>permissions</td>
            <td class="align-top">
                
                <code><a href="#getapplicationoauth2permission">List[Get<wbr>Application<wbr>Oauth2Permission]</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} the Object ID of the Azure Active Directory Application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of User Object IDs that are assigned ownership of the application registration.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reply_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">required_<wbr>resource_<wbr>accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccess">List[Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The type of the permission
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Supporting Types

#### GetApplicationAppRole
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#GetApplicationAppRole">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#GetApplicationAppRole">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationAppRole.html">output</a> API doc for this type.
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
            <td class="align-top">Allowed<wbr>Member<wbr>Types</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies whether this app role definition can be assigned to users and groups, or to other applications (that are accessing this application in daemon service scenarios). Possible values are: `User` and `Application`, or both.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Permission help text that appears in the admin app assignment and consent experiences.
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
Display name for the permission that appears in the admin consent and app assignment experiences.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
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
            <td class="align-top">Allowed<wbr>Member<wbr>Types</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies whether this app role definition can be assigned to users and groups, or to other applications (that are accessing this application in daemon service scenarios). Possible values are: `User` and `Application`, or both.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Permission help text that appears in the admin app assignment and consent experiences.
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
Display name for the permission that appears in the admin consent and app assignment experiences.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
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
            <td class="align-top">allowed<wbr>Member<wbr>Types</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies whether this app role definition can be assigned to users and groups, or to other applications (that are accessing this application in daemon service scenarios). Possible values are: `User` and `Application`, or both.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Permission help text that appears in the admin app assignment and consent experiences.
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
Display name for the permission that appears in the admin consent and app assignment experiences.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
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
            <td class="align-top">allowed<wbr>Member<wbr>Types</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Specifies whether this app role definition can be assigned to users and groups, or to other applications (that are accessing this application in daemon service scenarios). Possible values are: `User` and `Application`, or both.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Permission help text that appears in the admin app assignment and consent experiences.
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
Display name for the permission that appears in the admin consent and app assignment experiences.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetApplicationOauth2Permission
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/input/#GetApplicationOauth2Permission">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#GetApplicationOauth2Permission">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#GetApplicationOauth2PermissionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#GetApplicationOauth2Permission">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationOauth2PermissionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationOauth2Permission.html">output</a> API doc for this type.
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
            <td class="align-top">Admin<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
The type of the permission
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the user consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the user consent
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
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
            <td class="align-top">Admin<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
The type of the permission
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the user consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the user consent
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
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
            <td class="align-top">admin<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
The type of the permission
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the user consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the user consent
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
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
            <td class="align-top">admin<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the admin consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Determines if the app role is enabled.
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
The type of the permission
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The description of the user consent
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The display name of the user consent
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
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetApplicationRequiredResourceAccess
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#GetApplicationRequiredResourceAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#GetApplicationRequiredResourceAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationRequiredResourceAccess.html">output</a> API doc for this type.
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
            <td class="align-top">Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccessresourceaccess">List&lt;Pulumi.<wbr>Azuread.<wbr>Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier for the resource that the application requires access to.
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
            <td class="align-top">Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccessresourceaccess">[]Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier for the resource that the application requires access to.
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
            <td class="align-top">resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccessresourceaccess">Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier for the resource that the application requires access to.
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
            <td class="align-top">resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#getapplicationrequiredresourceaccessresourceaccess">List[Get<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>App<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier for the resource that the application requires access to.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetApplicationRequiredResourceAccessResourceAccess
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#GetApplicationRequiredResourceAccessResourceAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#GetApplicationRequiredResourceAccessResourceAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.GetApplicationRequiredResourceAccessResourceAccess.html">output</a> API doc for this type.
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
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
The type of the permission
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
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
The type of the permission
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
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique identifier of the `app_role`.
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
The type of the permission
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
 (Required)
The unique identifier of the `app_role`.
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
The type of the permission
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







